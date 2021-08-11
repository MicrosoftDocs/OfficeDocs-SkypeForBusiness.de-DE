---
title: Aktivieren Teams-Räume für die Teilnahme an Besprechungen von Drittanbietern
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
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie Ihre Organisation und Ihre Teams-Räume für die Teilnahme an Cisco WebEx und Zoom unterstützen.
ms.openlocfilehash: 9857c4dee31c02c96212ccead33408b9e55b989de5b00d1d38aa975dc0413aab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275931"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Aktivieren Teams Raumgeräten für die Teilnahme an Besprechungen von Drittanbietern

Microsoft Teams-Räume-Geräte unterstützen eine One-Touch-Erfahrung für die Teilnahme an Onlinebesprechungen von Drittanbietern, die auch als direkte Gast-Teilnahme bezeichnet wird. Wenn die Funktion aktiviert ist, können Sie ein Teams-Räume-Gerät verwenden, um an Besprechungen teilzunehmen, die auf Cisco WebEx und Zoom gehostet werden, genauso einfach wie Sie an Besprechungen teilnehmen können, die in ihrer Microsoft Teams.

Bevor Sie von einem Mobile-Gerät aus an Drittanbieterbesprechungen Teams-Räume können, müssen Sie die folgenden Schritte tun:

1. Konfigurieren Sie Teams-Räume Postfach des Exchange Online-Raum, um Einladungen für Besprechungen von Drittanbietern zu verarbeiten.
2. Stellen Sie sicher, dass Ihre Organisation über keine Richtlinien zum Verhindern der Verbindung zu Besprechungsdiensten von Drittanbietern verfügen würde.
3. Konfigurieren Sie Ihre Teams-Räume-Geräte so, dass Besprechungen von Drittanbietern zulässig sind.

In den folgenden Abschnitten erfahren Sie, wie Sie die einzelnen Schritte ausführen.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Schritt 1: Zulassen, dass Kalender-Einladungen für Besprechungen von Drittanbietern verarbeitet werden

Um eine One-Touch Join-Erfahrung von einem Teamraumgerät aus zu aktivieren, müssen Sie als Erstes die Kalenderverarbeitungsregeln für das Postfach des Exchange Online Geräts festlegen. Das Raumpostfach muss externe Besprechungen zulassen und den Nachrichtentext und den Betreff behalten, damit die für die Teilnahme an der Drittanbieterbesprechung benötigte URL angezeigt wird. Gehen Sie wie folgt vor, um diese Raumpostfachoptionen mit dem [Cmdlet Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) festlegen:

1. Verbinden Sie Exchange Online PowerShell. Weitere Informationen finden Sie unter Verbinden verwenden Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) mit Standardauthentifizierung oder Verbinden, Exchange Online [PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)mithilfe der mehrstufigen Authentifizierung verwenden zu können, je nach Ihrer Authentifizierungsmethode.

2. Wenn Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Raumpostfachs nicht kennen, verwenden Sie den folgenden Befehl:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Suchen Sie den Namen des Raumpostfachs, das Ihrem Teams-Räume zugeordnet ist, und notieren Sie sich dessen UPN.

4. Nachdem Sie den UPN des Raumpostfachs finden, führen Sie den folgenden Befehl aus. Ersetzen `<UserPrincipalName>` Sie durch den UPN des Raumpostfachs:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Weitere Informationen zu [Exchange Online PowerShell.](/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Schritt 2: Konfigurieren Office 365 Threat Protection und Neuschreibung von Links

Um die Teilnahme mit nur einer Touch-Touch-Verbindung zu ermöglichen, müssen die Linkinformationen der Drittanbieter-Besprechung in der Besprechungs-Einladung vorhanden und lesbar sein. Wenn Ihre Organisation das Feature [Office 365 Advanced Threat Protection Tresor Links](/microsoft-365/security/office-365-security/atp-safe-links) verwendet, oder wenn Sie eine Drittanbieterlösung verwenden, die alle eingehenden und ausgehenden URLs auf Bedrohungen überprüft, kann dies die Teilnahme-URLs der Besprechung ändern und dafür sorgen, dass die Besprechung auf dem Teams-Räume-Gerät nicht mehr Teams-Räume kann. Um sicherzustellen, dass dies nicht geschieht, müssen Sie die URLs des Drittanbieter-Besprechungsdiensts zur ATP-Liste Tresor Links "Nicht neu schreiben" oder zur URL-Neuschreibungsliste des Drittanbieters hinzufügen.

Führen Sie die Schritte unter Einrichten einer benutzerdefinierten Liste "Nicht umschreiben-URLs mit AT Tresor P-Tresor-Links" aus, um der LISTE "NICHT umschreiben"-LINKS [DRITTANBIETER-BESPRECHUNGsdienst-URLs hinzuzufügen.](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Wenn Sie eine Drittanbieterlösung verwenden, lesen Sie die Anweisungen für diese Lösung, um der URL-Neuschreibungsausnahmeliste URLs hinzuzufügen.

Im Folgenden finden Sie einige Beispieleinträge, die Sie Ihrer ATP-Liste Tresor Links "Nicht umschreiben" oder URL-Neuschreibung der Drittanbieter-URL hinzufügen müssen:

- **Cisco WebEx**`*.webex.com*`
- **Zoomen** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`

Wenn Sie eine vollständige Liste der URLs, die Sie Zu Ihrer ATP-Liste hinzufügen Tresor Links "Nicht umschreiben"- oder URL-Neuschreibungsliste von Drittanbietern erhalten möchten, wenden Sie sich an den Drittanbieter für Besprechungsdienste, von dem Sie Besprechungs-Einladungen annehmen möchten. 

> [!CAUTION]
> Fügen Sie Ihrer ATP-Liste nur URLs hinzu, Tresor Links "Nicht umschreiben"- oder URL-Neuschreibung der Drittanbieter-Ausnahmeliste.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Schritt 3: Aktivieren von Drittanbieterbesprechungen auf einem Gerät

Der letzte Schritt, den Sie tun müssen, besteht im Zulassen, Teams-Räume Gerät an Besprechungen von Drittanbietern teilnehmen kann. Besprechungen von Drittanbietern benötigen einen Benutzernamen und eine E-Mail-Adresse, um an ihnen teilzunehmen. Wenn sich der Benutzername und die E-Mail-Adresse, die Sie verwenden müssen, vom Raumpostfach des Geräts unterscheiden, müssen Sie sie zu Ihrem Gerät hinzufügen. Dies können Sie in den Geräteeinstellungen oder in der XML-Konfigurationsdatei tun.

### <a name="use-device-settings"></a>Verwenden von Geräteeinstellungen

Gehen Sie wie folgt Teams-Räume um das Gerät mit dem Touchscreen zu konfigurieren:

1. Wählen Sie Microsoft Teams-Räume Gerät mehr **... aus.**
2. Wählen **Einstellungen** aus, und geben Sie dann den Benutzernamen und das Kennwort des Geräteadministrators ein.
3. Wechseln Sie zur Registerkarte **Besprechungen,** und wählen Sie **Cisco WebEx**, **Zoom** oder beides aus.
4. Wenn Sie an Besprechungen mit dem Benutzernamen und der E-Mail-Adresse teilnehmen möchten, die dem Raumpostfach zugeordnet sind, wählen Sie **Mit Rauminformationen teilnehmen aus.**
5. Wenn Sie an Besprechungen mit einem alternativen  Benutzernamen und einer E-Mail-Adresse teilnehmen möchten, wählen Sie Mit benutzerdefinierten Informationen teilnehmen aus, und geben Sie den Benutzernamen und die E-Mail-Adresse ein, die Sie verwenden möchten.
6. Wählen **Sie Speichern und beenden aus.** Ihr Gerät wird neu gestartet.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Verwenden der SkypeSettings.xml Konfigurationsdatei

Die folgenden Einstellungen können der Datei in `SkypeSettings.xml` hinzugefügt `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` werden. Weitere Informationen zu der Datei finden Sie `SkypeSettings.xml` unter Verwalten einer [Microsoft Teams-Räume-Konsoleneinstellungen remote mit einer XML-Konfigurationsdatei.](xml-config-file.md)

Um Cisco WebEx-Besprechungen zu ermöglichen, legen Sie `WebExMeetingsEnabled` das XML-Element wie folgt **auf True**(wahr) dar.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Legen Sie zum Aktivieren von Zoombesprechungen `ZoomMeetingsEnabled` das XML-Element wie folgt auf **True**(wahr) vor.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Sie können optional einen benutzerdefinierten Benutzernamen und eine benutzerdefinierte E-Mail-Adresse angeben, um mithilfe der folgenden XML-Elemente an Besprechungen von Drittanbietern teilzunehmen. Wenn die von Ihnen angegebenen Werte ungültig sind, verwendet das Teams-Räume standardmäßig den Benutzernamen und die E-Mail-Adresse des Raumpostfachs.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Um von einem Teams-Räume-Gerät aus an einer Cisco WebEx-Besprechung teilzunehmen, muss die Cisco-Besprechung in WebEx-Besprechungen Pro mit Cisco WebEx WebEx Web Application Version 40.7 oder höher gehostet werden. 
