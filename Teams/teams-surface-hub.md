---
title: Bereitstellen von Microsoft-Teams für die Fläche Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Konfigurieren von Admin-Einstellungen für Microsoft-Teams für Fläche Hub.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 251cc2d12dfdab2e9bc4c9bcc928e80a9c43e2c2
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "23938000"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Bereitstellen von Microsoft-Teams für die Fläche Hub
======================================

Vor der Bereitstellung von Microsoft-Teams für Microsoft Surface Hub Achten Sie darauf, dass Sie die Hardware, Betriebssystem und andere Voraussetzungen erfüllt sind. Weitere Informationen finden Sie im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).

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

7\. Im nächsten Schritt müssen Sie das Gerät Konto mit Teams für Hub-Oberfläche aktivieren. Stellen Sie sicher, dass die Umgebung die Anforderungen im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/)definierten erfüllt.

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

Diese Anweisungen sind für die Installation von Teams für Fläche Hub aus dem Microsoft Store. 
 
1. Starten Sie den Microsoft-Speicher:<br>
   a. Tippen Sie auf **Start** > **Alle Apps** > **Settings**.<br> b. Tippen Sie auf **Konto Fläche Hub-Gerät, Management**.<br>
   c. Tippen Sie auf der linken Seite auf der Registerkarte **Apps und -Features** .<br> d. Tippen Sie auf der rechten Seite auf die Schaltfläche **Öffnen Store** . 
2. Suchen Sie nach *Microsoft-Teams*, aus dem Microsoft Store. Die **Microsoft-Teams Fläche Hub** wird angezeigt. Tippen Sie auf die Schaltfläche **rufen Sie die app** zu installieren.  
3. Wenn die Installation abgeschlossen ist, starten Sie Fläche Hub neu. 

> [!NOTE]
> Tippen Sie nicht auf aus dem Angebot Seite Speicher **zu starten** .

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Stellen Sie die Standardeinstellung Anruf- und Besprechungen Anwendung Teams
 
Es gibt zwei Optionen für die Anruf- und Besprechungen Anwendung Standardrichtlinie konfigurieren: 

- **Option 1**: Konfigurieren von über USB-Schlüssel. 
- **Option 2**: über MDM wie Intune konfigurieren.
 
### <a name="option-1-configure-via-usb-key"></a>Option 1: Konfigurieren von über USB-Schlüssel 
 
Die Pakete finden Sie auf dieser [Seite herunterladen](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Wählen Sie die entsprechenden für das Paket, das Sie planen, installieren und kopieren Sie ihn in einen USB-Schlüssel. Die richtigen .ppkg-Datei verwenden, hängt die Standardrichtlinie für die Anwendung wie folgt anwenden möchten: 

|Number  |Beschreibung  |
|---------|---------|
|0     | Bevorzugter Skype-app auf der Startseite, Teams Besprechungen verfügbar        |
|1     | Teams bevorzugte app auf der Startseite, Skype Besprechungen verfügbar        |
|2     | Teams exklusive app auf der Startseite (Skype-app nicht verfügbar)        |
 
1. Fügen Sie den USB-Schlüssel an die Fläche Hub-Gerät. 
2. Öffnen Sie die **Einstellungen** app auf einem Gerät Fläche Hub. 
3. Öffnen Sie die **Fläche Hub Gerätemanagement Konto**.
4. Öffnen Sie die **Verwaltung von Geräten**. 
5. Klicken Sie auf **Hinzufügen oder Entfernen einer Bereitstellung Paket**. 
6. Klicken Sie auf **Paket hinzufügen**.
7. Wählen Sie aus dem Dropdown-Menü die Option **Wechselmedium** aus. 
8. Fügen Sie das entsprechende **TeamsRTMMode*.ppkg** -Paket, das zuvor an den USB-Schlüssel kopiert wurde. 
9. Starten Sie das Fläche Hub-Gerät neu. 
10. Nach dem Neustart des Geräts, sollten Sie möglicherweise die Teams app aus dem Bildschirm Start starten und teilnehmen an einer Besprechung aus dem Kalender. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Option 2: Konfigurieren von über MDM wie Intune 

Verwenden Sie Folgendes, um die Anruf- und Besprechungen Anwendung Standardrichtlinie über Intune konfigurieren.

|Einstellung   |Wert    |Beschreibung    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Datentyp | Ganzzahl (0-2)   |0 – bevorzugte Skype-app auf der Startseite, Teams Besprechungen verfügbar<br>1 – Teams bevorzugte app auf der Startseite, Skype Besprechungen verfügbar<br>2 - Teams exklusive app auf der Startseite (Skype-app nicht verfügbar) |
|Betrieb| Abrufen, festlegen        |

|Einstellung   |Wert    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Datentyp | String - Set-Zeichenfolge, die Teams Anwendungspaket-ID als **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Betrieb| Abrufen, festlegen        |

Starten Sie das Fläche Hub-Gerät neu. Nach dem Neustart des Geräts, sollten Sie möglicherweise die Teams app aus dem Bildschirm Start starten und teilnehmen an einer Besprechung aus dem Kalender.

> [!NOTE]
> Wenn das Gerät oder die Geräte Ihrer Organisation nicht aktuell Teil der Windows-Insider-Anwendung sind, und Sie befinden sich in Ländern behandelt durch allgemeine Data Protection Regulierung (GDPR) (oder Einstelllungen Telemetrie Basisdatenträger manuell geändert haben), müssen Sie erneut überprüfen dass Sie vollständige Telemetrie zulässig haben, bevor Sie die Insider Programm teilnehmen. GDPR geändert, das Standardverhalten des Fläche Hub-Geräte in der EU für grundlegende Telemetrie festzulegen.
