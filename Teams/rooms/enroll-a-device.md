---
title: Registrieren eines Teams-Geräts für verwaltete Dienste
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Onboarding Teams-Räume zu verwalteten Diensten
f1keywords: ''
ms.openlocfilehash: 4261e93a7bfab5d21620f8dbb327575352062c86
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2022
ms.locfileid: "63689151"
---
# <a name="enroll-device-into-managed-service"></a>Registrieren des Geräts beim verwalteten Dienst

Die Bereitstellung erfordert das Microsoft Teams-Räume von Geräten in Microsoft Teams-Räume verwalteten Diensten. Der Überwachungsdienst-Agent ist für die Verwendung mit zertifizierten MICROSOFT TEAMS(MTR)-Systemen und Peripheriegeräten verwendet.

## <a name="prerequisites"></a>Voraussetzungen

Führen Sie die folgenden Verfahren aus, um Ihre Hardware vor dem Registrierungsvorgang zu einrichten:

### <a name="adding-proxy-settings-optional"></a>Hinzufügen von Proxyeinstellungen (optional)

1. Melden Sie sich als Administrator an, indem [Sie als Administrator des MTR-Geräts Vorgänge ausführen.](#performing-operations-as-the-admin-user-of-the-mtr-device)
1. Geben Sie Windows ***Search** _-Feld (Abschnitt unten links auf dem Bildschirm) _ *cmd** ein (drücken Sie entweder lange auf den Bildschirm, oder wählen Sie nach rechts aus, und wählen Sie Als Administrator **_ausführen aus_**).  
1. Führen Sie den folgenden Befehl aus (doppelte Anführungszeichen am Ende des Befehls sind wichtig):
   - Bei Verwendung eines einzelnen ***Proxyservers***: bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""

      *Beispiel:* bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
      

   - Bei Verwendung einer ***Pac-Datei*** : bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>

      
      *Beispiel:* bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
      

### <a name="enabling-tpm-settings"></a>Aktivieren von TPM-Einstellungen

> [!NOTE]
> TPM muss für die Registrierung beim verwalteten Dienst aktiviert sein.

Wenn TPM auf einem Intel NUC-Gerät deaktiviert ist, aktivieren Sie TPM auf diesen Geräten wie folgt:  

1. Schließen Sie die Tastatur an ein NUC-Gerät an.  
1. Gerät neu starten.  
1. Zum Anzeigen des BIOS-Bildschirms drücken Sie schnell **F2**.  
1. Wählen Sie **Erweitert aus**.  
1. Wählen Sie **Sicherheit aus**.  
1. Aktivieren Sie rechts unter Sicherheitsfeatures die **Intel Platform Trust-Technologie**.  
1. Drücken Sie **F10, um Ihre Einstellungen zu speichern**.  
1. Wählen Sie im Bestätigungsfeld Ja **aus**. 
## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Ausführen von Vorgängen als Administratorbenutzer des MTR-Geräts

Bei einigen Konfigurations-/Installationsprozeduren müssen Sie sich als Administrator beim Gerät anmelden.

So melden Sie sich als Administrator (lokaler Administrator) beim Gerät an:

1. Stellen Sie sicher, dass Sie bei laufenden Anrufen auflegen und zum Startbildschirm zurückkehren.
1. Wählen Sie Microsoft Teams der Benutzeroberfläche des Microsoft Teams-Raum die Option Mehr und dann **Einstellungen** aus. Dort werden Sie auf dem Gerät zur Eingabe des lokalen Administratorkennworts aufgefordert (das Standardkennwort ist **_sFB_**).
1. Wählen **Einstellungen** und dann die Option Windows Einstellungen **, um auf** Windows Administrator zu zugreifen.  

1. Wählen Sie in der Liste der Benutzer, die im Anmeldebildschirm Windows angezeigt werden, **Administrator** (oder den jeweiligen lokalen Administrator Ihres Geräts) aus.

> [!NOTE]
> Wenn der Computer Mitglied einer Domäne *ist, wählen* Sie Anderer **Benutzer aus,** und verwenden Sie dann **.\admin** oder den Benutzernamen des lokalen Administrators, der auf dem Gerät als Benutzername konfiguriert wurde.  

So kehren Sie zur App Microsoft Teams Raum" zurück, nachdem Sie die erforderlichen Verwaltungsaufgaben ausgeführt haben:

1. Melden Sie Windows ***Startmenü*** Administratorkonto ab.
1. Kehren Sie Microsoft Teams zu Ihrem Raum zurück, indem Sie das Benutzerkontosymbol ganz links auf dem Bildschirm und dann **Skype.**

> [!NOTE]
> Wenn der Skype nicht aufgeführt ist, wählen Sie Anderer Benutzer aus, geben Sie ***".\skype***" als Benutzernamen ein, und melden Sie sich an.

 

## <a name="urls-required-for-communication"></a>Für Kommunikation erforderliche URLs

 > [!NOTE]
 > Der sämtliche Netzwerkdatenverkehr zwischen dem MTR-Geräte-Agent und dem Microsoft Teams-Räume – Managed Services-Dienstportal ist SSL über Port 443 *.*  Siehe [Office 365 von URLs und IP-Adressbereichen – Microsoft 365 Enterprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Die folgenden Hosts müssen zulässig sein, wenn Sie die **AllowList** für Datenverkehr in Ihrer Unternehmensumgebung aktiviert haben:

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

Der Registrierungsvorgang umfasst die folgenden Schritte:  

1. Erweitern Sie auf der linken Navigationsleiste des Microsoft Teams-Räume – Verwaltete Dienste [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)die Option **Einstellungen und wählen** Sie **Allgemein aus**.  
1. Wählen *Sie unter Einen Raum registrieren* die Option **Installationsprogramm herunterladen aus**  , um die Monitoring Agent-Software herunterzuladen.
1. **Optional:** Einrichten von Proxyeinstellungen für den Agent siehe [Hinzufügen von Proxyeinstellungen (optional).](#adding-proxy-settings-optional)
1. Installieren Sie das Agent-Installationsprogramm (heruntergeladen in Schritt 2) auf MTR-Einheiten, entweder durch lokales Ausführen der MSI auf einem MTR-Gerät oder über Ihr normales Veröffentlichungsmittel für MSI-Anwendungen auf Geräten in Ihrer Umgebung (Gruppenrichtlinien usw.)  
1. Der Raum wird innerhalb von 5 bis 10 Minuten im Portal angezeigt. Wenn nicht, wenden Sie sich an managedroomsupport@microsoft.com.  

   ![Screenshot von Einstellungen und Schlüsseln zur Selbstregistrierung](../media/software-installation-005new.png)
 
> [!NOTE]
> Wenn Sie den Agent installieren müssen, ohne dass die Teams-App auf der MTR sich bei Teams anmelden kann, können Sie unseren Registrierungsschlüssel als optionalen Prozess verwenden. Wechseln Sie zu "?".  (Hilfe) in der oberen rechten Ecke des Portals, und wählen Sie dann "Downloadtaste (optional)" aus. Platzieren Sie bei der Installation des Agents den (zuvor aus dem Portal heruntergeladenen) Selbstregistrierungsschlüssel im Verzeichnis  **C:\Rigel**  des Geräts.

## <a name="installation"></a>Installation

Nachdem Sie das Installationsprogramm von Microsoft heruntergeladen haben (entweder über das Portal oder mithilfe der oben bereitgestellten AKA.ms-URL), entzippen Sie den Inhalt, um auf die Datei **ManagedRoomsInstaller.msi.**

Es gibt zwei Installationsmodi: 1) Installation einzelner lokaler Computer und 2) Masseninstallationsmodus (in der Regel über Gruppenrichtlinien ähnlicher Methode). Wir empfehlen die individuelle Installation für Computer ohne Domänenverbindung oder für Computer, auf der Sie MSI-Installationsprogramme nicht remote ausführen können.  

Aufgrund der vielen verschiedenen Möglichkeiten, wie Kunden MSI-Anwendungen im Massenbereitstellungsmodus ausführen können, führt dieses Dokument nur die Installation im individuellen Modus durch.  
## <a name="individual-devicemdashdomain-joined-walkthrough"></a>Exemplarische Vorgehensweise mit einer einzelnen DeviceDomain-Mitglied&mdash;

1. Melden Sie sich als Administrator beim Gerät an. Stellen Sie *sicher, dass ausführende Vorgänge als Administratorbenutzer der Geräteschritte* befolgt werden.

1. Kopieren Sie die **ManagedRoomsInstaller.msi** auf das MTR-Gerät.

   Beim Ausführen des ***ManagedRoomsInstaller.msi*** wird ein Bildschirm "Lizenzvertrag" angezeigt.

1.  Nachdem Sie den Vertrag gelesen haben, überprüfen Sie *Ich akzeptiere die **Bedingungen im** Lizenzvertrag_, und drücke _*Install**.  

    Damit beginnt die Microsoft Teams-Räume – Managed Services Monitoring Softwareinstallation. Eine Eingabeaufforderung zur Erhöhung (als Administrator ausführen) wird angezeigt.

 1. Wählen Sie **Ja aus**.

    Die Installation wird fortgesetzt. Während des Installationsvorgang wird ein Konsolenfenster geöffnet, in dem die letzte Phase der Überwachungssoftware Microsoft Teams-Räume – Managed Services gestartet wird.  

    > [!NOTE]
    > Schließen Sie das Fenster nicht. Nach Abschluss der Installation zeigt der Assistent die Schaltfläche "Fertig stellen" an.

## <a name="completing-enrollment"></a>Registrierung wird abgeschlossen

Nachdem die Installation abgeschlossen ist, warten Sie 5 bis 10 Minuten, und aktualisieren Sie das Portal. Dann wird das Gerät aufgelistet, das als *Onboarding-Status gemeldet* wird.

Im *Onboarding-Status* wird der Status des Raum angezeigt und aktualisiert, es werden jedoch keine Warnungen ausgelöst oder Untersuchungstickets erstellt.

Wählen Sie den Raum und dann **Registrieren aus**  , um Benachrichtigungen zu Vorfällen, Untersuchungstickets zu erhalten oder einen Vorfall zu melden.

Bei Fragen oder Problemen öffnen Sie bitte einen vom Kunden gemeldeten Vorfall im Portal oder managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Registrierung und Deinstallation von Überwachungssoftware

Um die Registrierung des Geräts aufzingen, entfernen Sie den Überwachungs-Agent wie folgt vom MTR-Gerät:

1. Melden Sie sich auf dem überwachten Gerät als Administrator an. Führen Sie unbedingt die Schritte unter *Ausführen von Vorgängen als Administratorbenutzer des Geräts aus*.
1. Laden Sie das Skript zum Zurücksetzen [von aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extrahieren Sie das Skript an einer anderen Stelle auf dem Gerät, und kopieren Sie den Pfad.
1. Öffnen Sie PowerShell als Administrator: Geben Sie im Feld Windows ***Search** _ (Abschnitt unten links auf dem Bildschirm) "PowerShell" ein, und klicken Sie mit der rechten Maustaste auf _*_Windows PowerShell_**.
1. Wählen *Sie "Als Administrator ausführen" aus,* und akzeptieren Sie die Eingabeaufforderung des UAC.
1. Geben *Sie Set-ExecutionPolicy –ExecutionPolicy RemoteSigned ein* , und drücken Sie bei der nächsten Eingabeaufforderung **Y** .  
1. Fügen Sie den vollständigen Pfad zum entpackten Offboarding-Skript in das PowerShell-Fenster ein, oder geben Sie ihn ein, und drücken Sie die **EINGABETASTE**.

   Beispiel:

   *C:\Users\admin\Downloads\MTRPDeviceOffboarding\_\_\MTRPDevice\_\_Offboarding.ps1*  

   Dadurch wird das Gerät auf Standard-MTR-Updates des Benutzers zurückgesetzt, und der MTRP-Überwachungs-Agent und die Dateien werden entfernt.

1. Wählen Sie auf der linken Seite im Microsoft Teams-Räume – Verwaltete Dienste die Option Räume **aus**.  
1. Wählen Sie in der Liste der bereitgestellten Räume den Raum aus, den Sie registrieren möchten,  und wählen Sie Registrierung entfernen aus, um keine Vorfallbenachrichtigungen oder Untersuchungstickets mehr zu erhalten, oder melden Sie einen Vorfall für den Raum.

## <a name="troubleshooting-table"></a>Problembehandlung in einer Tabelle

> [!NOTE]
> Alle Microsoft Teams-Räume – Überwachungsfehler bei verwalteten Diensten werden bei einer bestimmten Ereignisprotokolldatei mit dem Namen **"Microsoft Managed Rooms" protokolliert**. 

### <a name="application-runtime-log-file-location-"></a>***Speicherort der Protokolldatei der Anwendungslaufzeit*** =  

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortalVerboseLogFile.log\_\_, wobei **x.x.x** die Versionsnummer der App ist.

|**Symptom**  |**Empfohlenes Verfahren**  |
| :- | :- |
|<p>Sie erhalten eine Fehlermeldung mit der Angabe, dass   </p><p>***FEHLER: Führen Sie diese Anwendung mit** _ </p><p>_ *_elevated privileges_**  </p>|Führen Sie die Anwendung mit eskalierten Berechtigungen aus, und versuchen Sie es erneut.  |
|  |  |
|<p>Sie erhalten eine Fehlermeldung mit der Angabe, dass   </p><p>***TPM-Daten können nicht gefunden werden***  </p>|Stellen Sie sicher, dass das TPM (Trusted Platform Module) Ihres Geräts im BIOS aktiviert ist. Dies ist normalerweise in den Sicherheitseinstellungen des Geräte-BIOS zu finden.  |
|  |  |
|<p>Sie erhalten eine Fehlermeldung  </p><p>` `***FEHLER: Das lokale Benutzerkonto "Administrator" oder "Skype" wurde nicht gefunden***  </p>|Stellen Sie sicher, dass die Benutzerkonten auf dem zertifizierten Gerät Microsoft Teams Raumsysteme vorhanden sind.  |
|  |  |
|Sie erhalten alle Fehlermeldungen, die oben nicht behandelt werden.  |Bitte geben Sie eine Kopie Ihres Installationsprotokolls an Ihren Microsoft Teams-Supportmitarbeiter an. |
