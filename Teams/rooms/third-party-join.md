---
title: Aktivieren Teams-Räume Geräten für die Teilnahme an Besprechungen von Drittanbietern
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: In diesem Artikel wird erläutert, wie Sie Ihre Organisation und Teams-Räume Geräte konfigurieren, um die Teilnahme von Drittanbieterbesprechungen an Cisco Webex und Zoom zu unterstützen.
ms.openlocfilehash: 23eefeb564e3333b1bc2105a1fc4d57a0ff41bbe
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529677"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>Aktivieren Teams-Räume Geräten für die Teilnahme an Besprechungen von Drittanbietern

Microsoft Teams-Räume-Geräte unterstützen eine One-Touch-Erfahrung für die Teilnahme an Onlinebesprechungen von Drittanbietern, die auch als direkter Gastbeitritt bezeichnet werden. Wenn diese Option aktiviert ist, können Sie Teams-Räume verwenden, um an Besprechungen teilzunehmen, die auf Cisco Webex und Zoom gehostet werden, ebenso einfach wie an Besprechungen, die in Microsoft Teams gehostet werden.

Unterstützte Geräte und Dienste:

- MTR unter Windows, alle zertifizierten Modelle – Zoom, Cisco Webex

- MTR auf Android-, Poly-, Yealink- und Logitech-zertifizierten Modellen – Zoom

> [!NOTE]
> Um von einem Teams-Räume Gerät aus an einer Cisco Webex-Besprechung teilzunehmen, muss die Cisco-Besprechung in Webex Meetings Pro mit der Cisco Webex-Webanwendungsversion WBS 40.7 oder höher gehostet werden. 

Bevor Sie von Teams-Räume aus an Besprechungen von Drittanbietern teilnehmen können, müssen Sie die folgenden Schritte ausführen:

1. Konfigurieren Sie das Teams-Räume Exchange Online Raumpostfach, um Einladungen für Besprechungen von Drittanbietern zu verarbeiten.
2. Stellen Sie sicher, dass Ihre Organisation keine Richtlinien hat, die Sie daran hindern würden, eine Verbindung mit Besprechungsdiensten von Drittanbietern herzustellen.
3. Konfigurieren Sie Teams-Räume, um Besprechungen von Drittanbietern zuzulassen.

In den folgenden Abschnitten wird gezeigt, wie Sie die einzelnen Schritte ausführen.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Schritt 1: Zulassen der Verarbeitung von Kalendereinladungen für Besprechungen von Drittanbietern

Das erste, was Sie tun müssen, um eine One-Touch-Join-Erfahrung aus TeamRooms zu aktivieren, ist das Festlegen der Kalenderverarbeitungsregeln für das Exchange Online Raumpostfach des Geräts. Das Raumpostfach muss externe Besprechungen zulassen und den Nachrichtentext und den Betreff beibehalten, damit die url angezeigt werden kann, die für die Teilnahme an der Drittanbieterbesprechung erforderlich ist. Gehen Sie wie folgt vor, um diese Raumpostfachoptionen mithilfe des Cmdlets ["Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing.) " festzulegen:

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Weitere Informationen finden Sie je nach Authentifizierungsmethode unter [Herstellen einer Verbindung mit Exchange Online PowerShell mit Standardauthentifizierung](/powershell/exchange/connect-to-exchange-online-powershell) oder [Herstellen einer Verbindung mit Exchange Online PowerShell mithilfe der mehrstufigen Authentifizierung](/powershell/exchange/mfa-connect-to-exchange-online-powershell).

2. Rufen Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Raumpostfachs ab, wenn Sie ihn nicht kennen, indem Sie den folgenden Befehl ausführen:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Suchen Sie den Namen des Raumpostfachs, das Ihrem Teams-Räume Gerät zugeordnet ist, und notieren Sie sich dessen UPN.

4. Nachdem Sie den UPN des Raumpostfachs gefunden haben, führen Sie den folgenden Befehl aus. Ersetzen Sie `<UserPrincipalName>` den UPN des Raumpostfachs:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Erfahren Sie mehr über [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Schritt 2: Konfigurieren von Office 365 Threat Protection und Umschreiben von Links

Um die One-Touch-Teilnahme zu ermöglichen, müssen Informationen zu Besprechungsbeitrittslinks aus der Drittanbieterbesprechung in der Besprechungseinladung vorhanden und lesbar sein. Wenn Ihre Organisation das Feature [Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/safe-links) sichere Links verwendet oder wenn Sie eine Drittanbieterlösung verwenden, die alle eingehenden und ausgehenden URLs auf Bedrohungen überprüft, kann dies die URLs für Besprechungsbeitritte ändern und die Besprechung vom Teams-Räume Gerät nicht wiedererkennbar machen. Um sicherzustellen, dass dies nicht geschieht, müssen Sie die URLs des Drittanbieter-Besprechungsdiensts zu Defender für [Office 365 Liste sicherer Links **nicht neu schreiben**](/microsoft-365/security/office-365-security/safe-links) oder die URL-Ausnahmeliste des Drittanbieters neu schreiben.

 Wenn Sie eine Drittanbieterlösung verwenden, lesen Sie die Anweisungen für diese Lösung, um URLs zu ihrer URL-Ausnahmeliste zum Umschreiben hinzuzufügen.

Im Folgenden finden Sie einige Beispieleinträge, die Sie Möglicherweise zu Ihrer Defender für Office 365 Liste sicherer Links hinzufügen müssen: Liste *nicht neu schreiben* oder Ausnahmeliste für Url-Neuschreibungen von Drittanbietern:

- **Cisco Webex** `*.webex.com/*`
- **Zoom** `*.zoom.us/*`, , `*.zoom.com/*``*.zoomgov.com/*`

Eine vollständige Liste der URLs, die Sie Ihrer Defender für Office 365 Sichere Links hinzufügen können: Liste *nicht neu schreiben* oder Ausnahmeliste von Drittanbieter-URLs neu schreiben, wenden Sie sich an den Drittanbieter für Besprechungsdienst, von dem Sie Besprechungseinladungen annehmen möchten.

> [!CAUTION]
> Fügen Sie Ihrer Microsoft Defender für Office 365 Liste sicherer Links nur URLs hinzu, denen Sie vertrauen. Keine Liste *neu schreiben* oder Ausnahmeliste von Drittanbieter-URLs neu schreiben.

## <a name="step-3a-enable-third-party-meetings-on-teams-rooms-on-windows"></a>Schritt 3a: Aktivieren von Drittanbieterbesprechungen auf Teams-Räume unter Windows

Der letzte Schritt, den Sie ausführen müssen, besteht darin, Teams-Räume die Teilnahme an Besprechungen von Drittanbietern zu ermöglichen. Besprechungen von Drittanbietern erfordern einen Benutzernamen und eine E-Mail-Adresse, um an ihnen teilzunehmen. Wenn sich der Benutzername und die E-Mail-Adresse, die Sie verwenden müssen, vom Raumpostfach des Geräts unterscheiden, müssen Sie sie Ihrem Gerät hinzufügen. Sie können dies in den Teams-Räume-Einstellungen oder in der XML-Konfigurationsdatei tun. Sie können dies in den Teams-Räume-Einstellungen für alle geeigneten Teams-Räume oder in der XML-Konfigurationsdatei für Teams-Räume unter Windows tun.

### <a name="use-device-settings"></a>Verwenden von Geräteeinstellungen

Gehen Sie wie folgt vor, um Teams-Räume unter Windows mithilfe der Touchscreen-Konsole zu konfigurieren:

1. Wählen Sie auf der Microsoft Teams-Räume Konsole **"Weitere**" aus.
2. Wählen Sie **"Einstellungen"** aus, und geben Sie dann den Benutzernamen und das Kennwort des Geräteadministrators ein.
3. Wechseln Sie zur Registerkarte " **Besprechungen** ", und wählen Sie einen Drittanbieter für Besprechungen aus, den Sie aktivieren möchten (z. B. **Webex**, **Zoom** usw.).
4. Wenn Sie an Besprechungen mit dem Benutzernamen und der E-Mail-Adresse teilnehmen möchten, die dem Raumpostfach zugeordnet sind, wählen Sie **"Mit Rauminformationen teilnehmen"** aus.
5. Wenn Sie an Besprechungen mit einem alternativen Benutzernamen und einer alternativen E-Mail-Adresse teilnehmen möchten, wählen Sie **"Mit benutzerdefinierten Informationen teilnehmen** " aus, und geben Sie Benutzernamen und E-Mail-Adresse ein, die Sie verwenden möchten.
6. Wählen Sie **"Speichern" und "Beenden" aus**. Ihr Gerät wird neu gestartet.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Verwenden der Konfigurationsdatei für SkypeSettings.xml

Die folgenden Einstellungen können der `SkypeSettings.xml` Datei `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`in hinzugefügt werden. Weitere Informationen zur `SkypeSettings.xml` Datei finden [Sie unter Remoteverwaltung einer Microsoft Teams-Räume Konsoleneinstellungen mit einer XML-Konfigurationsdatei](xml-config-file.md).

Um Cisco Webex-Besprechungen zu aktivieren, legen Sie das `WebexMeetingsEnabled` XML-Element wie folgt auf **"True"** fest.

```xml
<WebexMeetingsEnabled>True</WebexMeetingsEnabled>
```

Um Zoombesprechungen zu aktivieren, legen Sie das `ZoomMeetingsEnabled` XML-Element wie folgt auf **"True"** fest.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Sie können optional einen benutzerdefinierten Benutzernamen und eine E-Mail-Adresse angeben, um mithilfe der folgenden XML-Elemente an Besprechungen von Drittanbietern teilzunehmen. Wenn die von Ihnen angegebenen Werte ungültig sind, verwendet das Teams-Räume Gerät standardmäßig den Benutzernamen und die E-Mail-Adresse des Raumpostfachs.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```
## <a name="step-3b-enable-third-party-meetings-on-teams-rooms-on-android"></a>Schritt 3b: Aktivieren von Drittanbieterbesprechungen auf Teams-Räume unter Android

Gehen Sie wie folgt vor, um Teams-Räume unter Android mithilfe der Touchscreen-Konsole oder der Front-of-Room-Anzeige zu konfigurieren:

1.  Wählen Sie auf der Microsoft Teams-Räume Konsole oder der Anzeige vor dem Raum **die Option "Mehr**" aus.
2.  Wählen Sie **"Einstellungen"** aus, und:
    -   Wenn Sie ein persönliches Konto verwenden (z. B. ein Konto mit einer E5-Lizenz), wählen Sie " **Besprechungen** " aus.
    -   Wenn Sie ein freigegebenes Konto verwenden (z. B. ein Ressourcenkonto mit einer Teams-Räume Lizenz), wählen Sie **"Geräteeinstellungen**", suchen Sie **teams Admin Einstellungen**, geben Sie ein Administratorkennwort ein, und wählen Sie eine **Besprechungsoption** aus.
      > [!NOTE]
      > Einige Gerätehersteller benötigen ein Administratorkennwort, bevor auf **geräteeinstellungen** zugegriffen werden kann.

    ![Besprechungseinstellungen für MTR unter Android](..\media\mtrandroid.png)

3.  Wählen Sie einen Drittanbieter für Besprechungen aus, den Sie aktivieren möchten.
4.  Wenn Sie an Besprechungen mit einem benutzerdefinierten Benutzernamen und einer E-Mail-Adresse teilnehmen möchten, wählen Sie **"Mit benutzerdefiniertem Namen und E-Mail teilnehmen**" aus. Um benutzerdefinierte persönliche Informationen zu aktualisieren, drücken **Sie "Benutzerdefinierte Informationen bearbeiten** ", und geben Sie Ihren bevorzugten Namen und Ihre E-Mail-Adresse ein.

