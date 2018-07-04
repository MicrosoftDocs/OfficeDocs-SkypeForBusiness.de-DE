---
title: Bereitstellen von Microsoft-Teams für die Fläche Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Konfigurieren von Admin-Einstellungen für Microsoft-Teams für Fläche Hub.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192180"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Bereitstellen von Microsoft-Teams für die Fläche Hub
======================================

Vor der Bereitstellung von Microsoft-Teams für Microsoft Surface Hub Achten Sie darauf, dass Sie die Hardware, Betriebssystem und andere Voraussetzungen erfüllt sind. Weitere Informationen finden Sie im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).

## <a name="set-up-user-accounts"></a>Einrichten von Benutzerkonten
 
Erstellen Sie zum Einrichten von Benutzerkonten, die mit den Teams für Fläche Hub verwendet werden kann das Gerät Konto wie für die Unterstützung bei Skype für Unternehmen. Das Gerät Konto benötigt mehrstufige Authentifizierung deaktiviert (um die automatische Anmeldung zulassen) für die folgenden Dienste in Office 365-Teams:  
- Exchange 
- SharePoint 
- Office-Apps 

## <a name="add-a-device-account"></a>Hinzufügen eines Gerätekontos 

1\. Starten Sie eine remote Windows PowerShell-Sitzung auf einem PC und eine Verbindung mit Exchange herstellen. Stellen Sie sicher, dass Sie die richtigen Berechtigungen die zugeordneten Cmdlets ausführen festgelegt haben. Es folgen einige Beispiele für Cmdlets, die in Ihrer Umgebung verwendet und geändert werden können.

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2\. Wenn Sie die Sitzung eingerichtet haben, erstellen Sie entweder ein neues Postfach und aktivieren es als „RoomMailboxAccount“, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch wird das Konto zum Teams authentifizieren.

Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

Wenn Sie ein neues Ressourcenpostfach erstellen:

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3\. Sie müssen verschiedene Exchange-Eigenschaften für das Gerätekonto festlegen, um die Besprechungsumgebung zu verbessern. Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

4\. Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure Active Directory herstellen. Führen Sie das folgende Cmdlet aus, um die Verbindung mit Azure AD herzustellen:

```
Connect-MsolService -Credential $cred
```

5\. 	Wenn das Kennwort nicht ablaufen soll, führen Sie das Cmdlet „Set-MsolUser“ mit der Option „PasswordNeverExpires“ wie folgt aus:   

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

Sie können auch wie folgt eine Telefonnummer für den Raum festlegen:

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

6\. Das Gerät Konto muss eine gültige Office 365-Lizenz verfügen, oder Exchange und Skype für Unternehmen funktionieren nicht. Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen. Get-MsolAccountSku können Sie wie folgt eine Liste der verfügbaren SKUs für Ihre Office 365-Mandanten abzurufen:
 
```
Get-MsolAccountSku
```

Als Nächstes können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

7\. Im nächsten Schritt müssen Sie das Gerät Konto mit Teams für Hub-Oberfläche aktivieren. Stellen Sie sicher, dass die Umgebung die Anforderungen im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/)definierten erfüllt.

Starten Sie wie folgt eine remote Windows PowerShell-Sitzung (unbedingt Skype für Business Online-PowerShell-Komponenten zu installieren):

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

Im nächsten Schritt aktivieren Sie Ihren Teams für Fläche Hub Konto durch Ausführen des folgenden Cmdlets:

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto-Setup wird, wie im folgenden Beispiel dargestellt:

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> Neue Benutzerkonten möglicherweise nicht im gleichen Registrar-Pool als vorhandenen Benutzerkonten in den Mandanten erstellt werden. Der vorangehenden Befehl wird verhindert, dass Fehler in kontoeinrichtung aufgrund dieser Situation. 

Nachdem Sie die vorhergehenden Schritte zum Aktivieren des Teams für Fläche Hub Konto abgeschlossen haben, müssen Sie die Fläche Hub v2 Gerät eine Lizenz zuweisen. Verwenden das administrative Office 365-Portal, das Gerät eine Oberfläche Hub-Lizenz-Teams zuweisen.

### <a name="assign-a-license-to-the-account"></a>Weisen Sie eine Lizenz für das Konto

1. Melden Sie sich als mandantenadministrator an, öffnen Sie das Office 365 Administrationscenter, und klicken Sie auf die Admin-app.
2. Klicken Sie auf **Benutzer und Gruppen**, und klicken Sie dann auf **Benutzer hinzufügen, Zurücksetzen von Kennwörtern, und vieles mehr**.
3. Wählen Sie die Teams für Fläche Hub-Konto, und klicken Sie oder tippen Sie auf das Stiftsymbol, das Möglichkeit zu bearbeiten.
4. Klicken Sie auf die Option **Lizenzen** .
5. Klicken Sie im Abschnitt **Lizenzen zuweisen** müssen Sie planen, je nach Ihrer Lizenzierung auswählen.
6. Klicken Sie auf **Speichern**, um die Aufgabe abzuschließen.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installieren von Teams für Fläche Hub aus dem Microsoft-Speicher 

Dabei werden die aktuellen problemumgehungen für die Installation von Teams für Fläche Hub aus dem Microsoft Store. 
 
1. Starten Sie den Windows Store:<br>
   a. Tippen Sie auf **Start** > **Alle Apps** > **Settings**.<br> b. Tippen Sie auf **Konto Fläche Hub-Gerät, Management**.<br>
   c. Tippen Sie auf der linken Seite auf der Registerkarte **Apps und -Features** .<br> d. Tippen Sie auf der rechten Seite auf die Schaltfläche **Öffnen Store** . 
2. Suchen Sie nach *Microsoft-Teams*, aus dem Microsoft Store. Die **Microsoft-Teams Fläche Hub (Preview)** wird angezeigt. Tippen Sie auf die Schaltfläche **rufen Sie die app** zu installieren.  
3. Wenn die Installation abgeschlossen ist, starten Sie Fläche Hub neu. 
4. Nach dem Neustart die Fläche Hub wird, werden Sie können die Teams app im Menü **Start** starten und teilnehmen an einer Besprechung aus dem Kalender. 

## <a name="make-teams-the-default-vtc-application"></a>Stellen Sie die standardanwendung VTC Teams

Teams können die standardmäßige VTC-Anwendung anstelle von Skype für Unternehmen werden bis zu festgelegt werden. Eine Richtlinie für Mobile Geräte Management (MDM) muss auf dem Gerät Fläche Hub angewendet werden soll. 
 
Es gibt zwei Optionen zum Konfigurieren von MDM Richtlinien: 

- Wenn Sie eine Richtlinie konfiguriert haben, fügen sie über die Geräte Management app hinzu. 
- Wenn Sie keine remote-Richtlinie konfiguriert haben, haben wir eine bereitgestellten Package-Datei, die auf einem USB-Schlüssel geladen werden kann.

### <a name="device-management-configuration"></a>Verwaltung der Gerätekonfiguration

Es folgt ein Beispiel für eine von einer zentralen MDM Zertifizierungsstelle konfigurierte MDM Richtlinie hinzufügen. Wenn Sie sich im Unternehmensnetzwerk sind, können Sie die folgenden Anweisungen, einschließlich Benutzerkonto wortwörtlich. 
 
1. Klicken Sie im Abschnitt **Verwaltung von Geräten** Tippen Sie auf **+**.<br>
   Das Dialogfeld **Verbindung mit arbeiten oder Schule herstellen** wird geöffnet. 
2. Geben Sie die Richtlinie e-Mail-Adresse und das Kennwort bei entsprechender Aufforderung.<br>
   **Hinweis:**  Es ist ein Fehler in das Betriebssystem, das automatisch die Benutzeroberfläche nicht aktualisiert wird, nachdem Sie Ihr Gerät Management-Konto eingegeben haben. Sie müssen zu schließen und erneut öffnen Einstellungen, um die angegebene Konto zu sehen. 
3. Es werde ein paar Minuten für die MDM Benutzerrichtlinien synchronisieren. Wenn Sie eine Synchronisierung erzwingen möchten, tippen Sie auf die Schaltfläche **MDM-Konto** ein, und tippen Sie dann auf die Schaltfläche **Info** . Dadurch wird das Fenster Info angezeigt, in dem Sie **Sync**tippen können. 
4. Zum bestätigen, dass Sie verfügen, was Sie benötigen, können Sie die Registrierung überprüfen. Zwei Schlüssel unter **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**sollte angezeigt werden. <br><br>
   Der **VtcAppMeetingHandlingMode** DWORD-Wert gibt an, dass Teams ist der Standard-app. Die folgenden Werte werden erkannt. <br><br>
    |Number | Wert   |
    |-------|---------|
    |0      | SkypePreferred            |
    |1      | VtcPreferred (Teams)      |
    |2      | VtcExclusive (nur Teams) |

    Die **VtcCallAppPackageId** ist der Name des installierten Teams-Pakets. Wenn dies nicht angezeigt, stellen Sie sicher, dass Sie das Paket Teams installiert haben und erneut synchronisieren. 
 
### <a name="configure-mdm-via-usb-key"></a>Konfigurieren von MDM über USB-Schlüssel 
 
Die Pakete finden Sie auf dieser [Seite herunterladen](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Wählen Sie die entsprechenden für das Paket, das Sie planen, installieren und kopieren Sie ihn in einen USB-Schlüssel. Die richtigen .ppkg zu verwendende Datei hängt davon ab, das Teams-Paket, das aus dem Speicher installiert wurde, und die Richtlinie (Skype exklusive, bevorzugter Skype, Teams bevorzugt, Teams Exclusive) gelten soll. 
 
1. Fügen Sie den USB-Schlüssel an die Fläche Hub-Gerät. 
2. Öffnen Sie die **Einstellungen** app auf einem Gerät Fläche Hub. 
3. Öffnen Sie die **Fläche Hub Gerätemanagement Konto**.
4. Öffnen Sie die **Verwaltung von Geräten**. 
5. Klicken Sie auf **Hinzufügen oder Entfernen einer Bereitstellung Paket**. 
6. Klicken Sie auf **Paket hinzufügen**.
7. Wählen Sie aus dem Dropdown-Menü die Option **Wechselmedium** aus. 
8. Fügen Sie die **Allowbuildspreview.ppkg**, und wählen Sie dann das Fläche Hub-Paket, den, das Sie hinzufügen möchten. 
9. Starten Sie das Fläche Hub-Gerät neu. 

> [!NOTE]
> Wenn das Gerät oder die Geräte Ihrer Organisation nicht aktuell Teil der Windows-Insider-Anwendung sind, und Sie befinden sich in Ländern behandelt durch allgemeine Data Protection Regulierung (GDPR) (oder Einstelllungen Telemetrie Basisdatenträger manuell geändert haben), müssen Sie erneut überprüfen dass Sie vollständige Telemetrie zulässig haben, bevor Sie die Insider Programm teilnehmen. GDPR geändert, das Standardverhalten des Fläche Hub-Geräte in der EU für grundlegende Telemetrie festzulegen.