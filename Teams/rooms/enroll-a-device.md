---
title: Registrieren eines Teams-Raumgeräts bei verwalteten Diensten
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 07/22/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Onboarding Teams-Räume Geräten in verwaltete Dienste
f1keywords: ''
ms.openlocfilehash: 07fbb2b196c0f74b34dbe2018865181e57aca17b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272040"
---
# <a name="enroll-device-into-managed-service"></a>Registrieren des Geräts beim verwalteten Dienst

Die Bereitstellung erfordert das Onboarding Microsoft Teams-Räume Geräten in die Microsoft Teams-Räume verwalteten Dienste. Der Überwachungsdienst-Agent ist für die Verwendung mit zertifizierten Microsoft Teams Room (MTR)-Systemen und Peripheriegeräten vorgesehen.

## <a name="prerequisites"></a>Voraussetzungen

Führen Sie die folgenden Verfahren aus, um Ihre Hardware einzurichten, bevor Sie den Registrierungsprozess starten:

### <a name="adding-proxy-settings-optional"></a>Hinzufügen von Proxyeinstellungen (optional)

1. Melden Sie sich als Administrator an, indem [Sie Vorgänge als Admin Benutzer des MTR-Geräts ausführen](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. Geben Sie im Windows ***Search** _-Feld (unterer linker Abschnitt des Bildschirms) _ *cmd** ein (langes Drücken des Bildschirms oder Rechtsauswahl, und wählen Sie **_"Als Administrator ausführen") aus_**.
1. Führen Sie den folgenden Befehl aus (doppelte Anführungszeichen am Ende des Befehls sind wichtig):

   - Bei Verwendung eines einzelnen ***Proxyservers***: `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *Beispiel:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - Bei Verwendung einer ***PAC-Datei*** : `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *Beispiel:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
     ```

### <a name="enabling-tpm-settings"></a>Aktivieren von TPM-Einstellungen

> [!NOTE]
> TPM muss für die Registrierung beim verwalteten Dienst aktiviert sein.

Wenn TPM auf einem Intel NUC-Gerät deaktiviert ist, aktivieren Sie TPM auf diesen Geräten wie folgt:

1. Schließen Sie die Tastatur an ein NUC-Gerät an.
1. Starten Sie das Gerät neu.
1. Drücken Sie schnell **F2**, um den BIOS-Bildschirm anzuzeigen.
1. Wählen Sie **"Erweitert**" aus.
1. Wählen Sie **"Sicherheit**" aus.
1. Aktivieren Sie auf der rechten Seite unter den Sicherheitsfeatures die **Intel Platform Trust Technology**.
1. Drücken Sie **F10**, um Ihre Einstellungen zu speichern.
1. Wählen Sie im Bestätigungsfeld " **Ja**" aus.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Ausführen von Vorgängen als Admin Benutzer des MTR-Geräts

Bei einigen Konfigurations-/Installationsverfahren müssen Sie sich beim Gerät als Administrator anmelden.

So melden Sie sich beim Gerät als Administrator an (lokaler Administrator):

1. Stellen Sie sicher, dass Sie alle laufenden Anrufe auflegen und zur Startseite zurückkehren.
1. Wählen Sie auf der Benutzeroberfläche des Microsoft Teams-Raums  **"Mehr**" und dann **"Einstellungen**" aus, wo Sie aufgefordert werden, das lokale Administratorkennwort auf dem Gerät einzugeben (das Standardkennwort ist **_sfb_**).
1. Wählen Sie **"Einstellungen"** und dann  **"Windows-Einstellungen"**  aus, um als lokaler Administrator auf Windows zuzugreifen.

1. Wählen Sie in der Liste der Benutzer, die auf dem Windows-Anmeldebildschirm angezeigt werden, den  **Administrator** (oder den jeweiligen lokalen Administrator Ihres Geräts) aus.

> [!NOTE]
> Wenn der Computer der *Domäne beigetreten* ist, wählen Sie **"Anderer Benutzer**" aus, und verwenden Sie dann **".\admin**" oder den Benutzernamen des lokalen Administrators, der auf dem Gerät als Benutzername konfiguriert ist.

So kehren Sie zur Microsoft Teams-Räume-App zurück, nachdem Sie die erforderlichen administrativen Aufgaben ausgeführt haben:

1. Melden Sie sich über das ***Windows-Startmenü*** vom Admin Konto ab.
1. Kehren Sie zu Microsoft Teams-Räume zurück, indem Sie das Benutzerkontosymbol ganz links auf dem Bildschirm und dann **Skype** auswählen.

> [!NOTE]
> Wenn der Skype-Benutzer nicht aufgeführt ist, wählen Sie "Anderer Benutzer" aus, geben Sie ***".\skype*** " als Benutzernamen ein, und melden Sie sich an.

## <a name="urls-required-for-communication"></a>Für die Kommunikation erforderliche URLs

 > [!NOTE]
 > Der gesamte Netzwerkdatenverkehr zwischen dem MTR-Geräte-Agent und dem Microsoft Teams-Räume – Managed Services-Dienstportal ist SSL über Port 443 *.*  Siehe [Office 365 URLs und IP-Adressbereiche – Microsoft 365 Enterprise | Microsoft-Dokumentation](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Die folgenden Hosts müssen zulässig sein, wenn die **Datenverkehrs-Zulassungsliste** in Ihrer Unternehmensumgebung aktiviert ist:

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="enrollment-process"></a>Registrierungsprozess

Der Registrierungsprozess umfasst die folgenden Schritte:

1. Erweitern Sie auf der linken Navigationsleiste des Portals [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)Microsoft Teams-Räume – Verwaltete Dienste **einstellungen**, und wählen Sie **"Allgemein**" aus.
1. Wählen *Sie unter "Raum registrieren*" die Option **"Installationsprogramm herunterladen**  " aus, um die Monitoring Agent-Software herunterzuladen.
1. **Optional:** Einrichten von Proxyeinstellungen für den Agent; siehe [Hinzufügen von Proxyeinstellungen (optional)](#adding-proxy-settings-optional).
1. Installieren Sie das Agent-Installationsprogramm (heruntergeladen in Schritt 2) auf MTR-Einheiten, indem Sie entweder das MSI lokal auf einem MTR-Gerät oder über Ihre normalen Methoden zum Massenveröffentlichung von MSI-Anwendungen auf Geräten in Ihrer Umgebung (Gruppenrichtlinie usw.) ausführen.
1. Der Raum wird innerhalb von 5-10 Minuten im Portal angezeigt. Wenn dies nicht der Tut, wenden Sie sich an managedroomsupport@microsoft.com.

   ![Screenshot der Einstellungen und Selbstregistrierungsschlüssel.](../media/software-installation-005new.png)

> [!NOTE]
> Wenn Sie den Agent installieren müssen, ohne dass sich die Teams-App auf dem MTR bei Teams anmelden kann, können Sie unseren Registrierungsschlüssel als optionalen Prozess verwenden. Gehe zu '?'  (Hilfe) in der oberen rechten Ecke des Portals, und wählen Sie dann "Schlüssel herunterladen (optional)" aus. Platzieren Sie bei der Installation des Agents den "Self-Enrollment Key" (zuvor aus dem Portal heruntergeladen) im **Verzeichnis C:\Rigel** des Geräts.

## <a name="installation"></a>Installation

Nachdem Sie das Installationsprogramm von Microsoft heruntergeladen haben (entweder über das Portal oder mithilfe der oben angegebenen AKA.ms URL), entzippen Sie dessen Inhalt, um auf die Datei **ManagedRoomsInstaller.msi** zuzugreifen.

Es gibt zwei Installationsmodi: 1) Installation einzelner lokaler Computer und 2) Massenbereit stellenmodus (in der Regel über Intune ähnlicher Methode). Wir empfehlen die einzelbetriebliche Installation für Nicht-Domänencomputer oder für Computer, auf denen Keine Möglichkeit besteht, MSI-Installationsprogramme remote auszuführen.

Aufgrund der vielfältigen Möglichkeiten, wie Kunden MSI-Anwendungen im Massenbereitstellungsmodus ausführen können, durchläuft dieses Dokument nur die Installation im individuellen Modus sowie massenhaft auf Intune registrierten Geräten.

### <a name="individual-device-installation"></a>Installation einzelner Geräte

1. Melden Sie sich als Administrator beim Gerät an. Stellen Sie sicher, dass die *Durchführungsvorgänge ausgeführt werden, wenn der Admin Benutzer der Geräteschritte* befolgt wird.

1. Kopieren Sie die Datei **ManagedRoomsInstaller.msi** auf das MTR-Gerät.

   Beim Ausführen des ***ManagedRoomsInstaller.msi*** ist ein Lizenzvertragsbildschirm.

1. Nachdem Sie die Vereinbarung gelesen haben, überprüfen Sie ***Ich akzeptiere die Bedingungen im Lizenzvertrag** _ und drücken Sie _*Install**.

    Dies beginnt mit der Softwareinstallation Microsoft Teams-Räume – Managed Services Monitoring. Eine Aufforderung zur Erhöhung (als Administrator ausführen) wird angezeigt.

1. Wählen Sie **"Ja**" aus.

    Die Installation wird fortgesetzt. Während des Installationsvorgangs wird ein Konsolenfenster geöffnet und beginnt die letzte Phase der Softwareinstallation Microsoft Teams-Räume – Managed Services Monitoring.

    > [!NOTE]
    > Schließen Sie das Fenster nicht. Nach Abschluss der Installation zeigt der Assistent die Schaltfläche "Fertig stellen" an.

### <a name="intune-enrolled-device-bulk-deployment"></a>Intune-registrierte Massenbereitstellung von Geräten

Die folgenden Komponenten sind Voraussetzungen für eine erfolgreiche Installation: 

- **Intune Registrierung**: Teams-Räume auf Windows-Geräten müssen bereits in Intune registriert sein.
  Weitere Informationen zum Registrieren von Teams-Räume auf Windows-Geräten in Intune finden [Sie unter Registrieren von Microsoft Teams-Räume auf Windows-Geräten mit Microsoft Endpoint Manager – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Azure AD-Gruppe mit allen Teams-Räume auf Windows-Geräten als Mitglieder** – eine in Azure AD erstellte Gruppe, die alle Teams-Räume auf Windows-Geräten enthält, die Teil des Microsoft Teams-Räume Premium-Diensts sein sollten. Diese Gruppe wird für die Bereitstellung des MTRP-Agents verwendet.
  
> [!NOTE]
> Sie können für diesen Zweck die Verwendung dynamischer Gruppen in Azure AD in Betracht ziehen. Weitere Informationen zur [Registrierung von Microsoft Teams-Räume auf Windows-Geräten mit Microsoft Endpoint Manager – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **MTRP-Agent-Installationsprogramm herunterladen**  – Laden Sie die ZIP-Datei des Agents herunter<https://aka.ms/serviceportalagentmsi>, und extrahieren Sie den Inhalt der ZIP-Datei (ManagedRoomsInstaller.msi) in einen lokalen temporären Ordner.

**So installieren Sie Intune**

1. Melden Sie sich beim [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) an.
1. Wählen Sie **"Apps** > **alle Apps** > **hinzufügen" aus**.
1. Wählen Sie im Bereich **"App-Typ auswählen** " unter **"Andere** **App-Typen" die Option "Branchen-App**" aus.
1. Klicken Sie auf **"Auswählen"**. Die Schritte **zum Hinzufügen der App** werden angezeigt. 
1. Klicken Sie im **Bereich "App hinzufügen** " auf **"App-Paketdatei auswählen"**.
   1. Wählen Sie im **Bereich "App-Paketdatei** " die Option  **"Durchsuchen**" aus. Wählen Sie dann die **ManagedRoomsInstaller.msi** Datei aus, die zuvor heruntergeladen wurde (siehe Abschnitt "Voraussetzungen").
   1. Wenn Sie fertig sind, wählen Sie im **Bereich "App-Paketdatei**" die Option **"OK**" aus, um die App hinzuzufügen.
1. Führen Sie auf der **Seite "App-Informationen** " die folgenden Änderungen aus:
   1. Publisher: Geben Sie **Microsoft Corporation ein**.
   1. App-Version ignorieren: Wählen Sie **"Ja**" aus.

      > [!NOTE]
      > Der MTRP-Agent aktualisiert sich selbst; Daher sollten Sie die App-Version explizit ignorieren (jede Basisversion kann automatisch aktualisiert werden).

   1. (Optional) Kategorie: Wählen Sie **"Computerverwaltung" aus**.
   
1. Klicken Sie auf **"Weiter** ", um die Seite **"Aufgaben** " anzuzeigen.
   1. Klicken Sie im Abschnitt **"Erforderlich** " auf **"+Gruppe hinzufügen** ", um auf eine Gruppe von Geräten für die Installation des Agents abzuzielen.
   1. Geben **Sie im Bereich "Gruppe auswählen** " den Gruppennamen in das Suchfeld ein (siehe oben die Voraussetzungen), klicken Sie auf die gewünschte **Gruppe** , und klicken Sie auf **"Auswählen"**.
      Weitere Informationen finden Sie unter [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten](https://go.microsoft.com/fwlink/?linkid=2202166) und [Zuweisen von Apps zu Gruppen mit Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2202270).
1. Klicken Sie auf **"Weiter** ", um die Seite **"Überprüfen + Erstellen** " anzuzeigen.
1. Überprüfen Sie die Werte und Einstellungen, die Sie für die App eingegeben haben. Wenn Sie fertig sind, klicken Sie auf **"Erstellen**", um die App Intune hinzuzufügen.

Sobald der Vorgang abgeschlossen ist, beginnen Ihre Geräte nach ein paar Minuten mit der Installation des MTRP-Agents.

> [!NOTE]
> Nach der Installation kann es bis zu acht Stunden dauern, bis der MTRP-Agent ein Selbstupdate auf die neueste Version ausführt und im MTRP-Portal aufgeführt wird.
Um die automatische Registrierung im MTRP-Portal zu beschleunigen, sollten Sie das MTR-Gerät nach der Agentbereitstellung neu starten.

## <a name="completing-enrollment"></a>Abschließen der Registrierung

Warten Sie nach Abschluss der Installation 5-10 Minuten, und aktualisieren Sie dann das Portal, um das Gerät in der Liste anzuzeigen, das als *Onboardingstatus* gemeldet wird.

Im *Onboardingstatus* wird der Status des Chatrooms angezeigt und aktualisiert, es werden jedoch keine Warnungen ausgelöst oder Untersuchungstickets erstellt.

Wählen Sie den Raum aus, und wählen Sie **"Registrieren"**  aus, um mit dem Empfang von Vorfallbenachrichtigungen, Untersuchungstickets oder der Meldung eines Vorfalls zu beginnen.

Öffnen Sie bei Fragen oder Problemen einen vom Kunden gemeldeten Vorfall im Portal, oder wenden Sie sich an managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Aufheben der Registrierung und Deinstallation von Überwachungssoftware

Um die Registrierung des Geräts aufzuheben, entfernen Sie den Überwachungs-Agent wie folgt vom MTR-Gerät:

1. Melden Sie sich auf dem überwachten Gerät als Administrator an. Führen Sie unbedingt die Schritte zum *Ausführen von Vorgängen als Admin Benutzer des Geräts* aus.
1. Laden Sie das Zurücksetzungsskript von [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding) herunter.
1. Extrahieren Sie das Skript an einer beliebigen Stelle auf dem Gerät, und kopieren Sie den Pfad.
1. Öffnen Sie PowerShell als Administrator: Geben Sie im Windows ***Search** _-Feld (abschnitt unten links auf dem Bildschirm) "Powershell" ein, und klicken Sie mit der rechten Maustaste auf "_*_Windows PowerShell_**".
1. Wählen Sie *"Als Administrator ausführen"* aus, und akzeptieren Sie die UAC-Eingabeaufforderung.
1. Geben Sie *"Set-ExecutionPolicy –ExecutionPolicy RemoteSigned" ein* , und drücken Sie bei der nächsten Eingabeaufforderung **Y** .
1. Fügen Sie den vollständigen Pfad zum entpackten Offboarding-Skript in das PowerShell-Fenster ein, oder geben Sie ihn ein, und drücken **Sie die EINGABETASTE**.

   Beispiel:

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   Mit diesem Befehl wird das Gerät auf standardmäßige MTR-Updates des Benutzers zurückgesetzt und der MTRP-Überwachungs-Agent und die Dateien entfernt.

1. Wählen Sie im linken Menü im Portal "Microsoft Teams-Räume – Verwaltete Dienste" die Option **"Räume**" aus.
1. Wählen Sie in der Liste der bereitgestellten Räume den Raum aus, den Sie aufheben möchten, und wählen Sie "Registrierung aufheben" aus, um keine **Vorfallbenachrichtigungen** oder Untersuchungstickets mehr zu erhalten, oder um einen Vorfall für den Raum zu melden.

## <a name="troubleshooting-table"></a>Problembehandlungstabelle

> [!NOTE]
> Alle Microsoft Teams-Räume – Überwachungsfehler bei verwalteten Diensten werden in einer bestimmten Ereignisprotokolldatei namens **Microsoft Managed Rooms** protokolliert.

***Speicherort der Anwendungslaufzeitprotokolldatei*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log, wobei **x.x.x** die Versionsnummer der App ist.

|Symptom|Empfohlenes Verfahren|
|---|---|
|Sie erhalten eine Fehlermeldung mit folgendem Hinweis: </p><p> ***FEHLER: Führen Sie diese Anwendung mit_ aus.** <br> _ *_Rechte mit erhöhten Rechten_**|Führen Sie die Anwendung mit eskalierten Berechtigungen aus, und versuchen Sie es erneut.|
|||
|Sie erhalten eine Fehlermeldung mit folgendem Hinweis: </p><p> ***TPM-Daten wurden nicht gefunden.***|Stellen Sie sicher, dass auf Ihrem Gerät TPM (Trusted Platform Module) im BIOS aktiviert ist. Dies ist in der Regel in den Sicherheitseinstellungen des Geräte-BIOS zu finden.|
|||
|Sie erhalten eine Fehlermeldung: </p><p> ***FEHLER: Das lokale Benutzerkonto mit dem Namen "Admin" oder "Skype" wurde nicht gefunden.***|Stellen Sie sicher, dass die Benutzerkonten auf dem zertifizierten Microsoft Teams Room-Systemgerät vorhanden sind.|
|||
|Sie erhalten alle Fehlermeldungen, die oben nicht behandelt werden.|Bitte geben Sie eine Kopie Ihres Installationsprotokolls an Ihren Microsoft Teams System-Support-Agent an.|
