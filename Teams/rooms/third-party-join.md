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
ms.localizationpriority: medium
description: In diesem Artikel wird erläutert, wie Sie Ihre Organisation und Ihre Teams-Räume für die Teilnahme an Cisco WebEx und Zoom unterstützen.
ms.openlocfilehash: d952df95a396e29ffcf393ded068a30459707218
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015245"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Aktivieren Teams von Raumgeräten für die Teilnahme an Besprechungen von Drittanbietern

Microsoft Teams-Räume-Geräte unterstützen eine One-Touch-Erfahrung für die Teilnahme an Onlinebesprechungen von Drittanbietern, die auch als direkte Gast-Teilnahme bezeichnet wird. Wenn die Funktion aktiviert ist, können Sie Teams-Räume für Besprechungen verwenden, die auf Cisco WebEx und Zoom gehostet werden, genauso einfach wie Sie an Besprechungen teilnehmen, die in ihrem Unternehmen Microsoft Teams.

Bevor Sie von einem Anderen aus an Besprechungen von Drittanbietern Teams-Räume können, müssen Sie die folgenden Schritte tun:

1. Konfigurieren Sie Teams-Räume Postfach des Exchange Online,um Einladungen für Besprechungen von Drittanbietern zu verarbeiten.
2. Stellen Sie sicher, dass Ihre Organisation über keine Richtlinien zum Verhindern der Verbindung zu Besprechungsdiensten von Drittanbietern verfügen würde.
3. Konfigurieren Teams-Räume, damit Besprechungen von Drittanbietern zulässig sind.

In den folgenden Abschnitten erfahren Sie, wie Sie die einzelnen Schritte ausführen.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Schritt 1: Zulassen, dass Kalender-Einladungen für Besprechungen von Drittanbietern verarbeitet werden

Als Erstes müssen Sie eine One-Touch Join-Erfahrung von Teamräumen aus aktivieren, um die Kalenderverarbeitungsregeln für das Postfach des Exchange Online Geräts festlegen. Das Raumpostfach muss externe Besprechungen zulassen und den Nachrichtentext und den Betreff behalten, damit die für die Teilnahme an der Drittanbieterbesprechung benötigte URL angezeigt wird. Gehen Sie wie folgt vor, um diese Raumpostfachoptionen mit dem [Cmdlet Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) festlegen:

1. Verbinden Sie Exchange Online PowerShell. Weitere Informationen finden Sie unter Verbinden, wie Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) mit Standardauthentifizierung verwendet werden kann, oder Verbinden, Exchange Online [PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)mithilfe der mehrstufigen Authentifizierung verwenden zu können, je nach Ihrer Authentifizierungsmethode.

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

Um die Teilnahme mit nur einer Touch-Touch-Verbindung zu ermöglichen, müssen die Linkinformationen der Drittanbieter-Besprechung in der Besprechungs-Einladung vorhanden und lesbar sein. Wenn Ihre Organisation das Feature [Office 365 Advanced Threat Protection Tresor Links](/microsoft-365/security/office-365-security/atp-safe-links) verwendet, oder wenn Sie eine Drittanbieterlösung verwenden, die alle eingehenden und ausgehenden URLs auf Bedrohungen überprüft, kann dies die Teilnahme-URLs der Besprechung ändern und dafür sorgen, dass die Besprechung auf dem Teams-Räume-Gerät nicht mehr zu erkennen ist. Um sicherzustellen, dass dies nicht geschieht, müssen Sie die URLs des Drittanbieter-Besprechungsdiensts zur ATP-Liste Tresor Links "Nicht neu schreiben" oder zur URL-Neuschreibungsliste des Drittanbieters hinzufügen.

Um der LISTE "Nicht umschreiben"-Links von ATP-Tresor-Links URLs von Drittanbietern für Besprechungsdienst hinzuzufügen, führen Sie die Schritte unter Einrichten einer benutzerdefinierten Liste "Nicht umschreiben-URLs mit [ATP-Tresor-Links" aus.](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Wenn Sie eine Drittanbieterlösung verwenden, lesen Sie die Anweisungen für diese Lösung, um der URL-Neuschreibungsausnahmeliste URLs hinzuzufügen.

Im Folgenden finden Sie einige Beispieleinträge, die Sie Möglicherweise Ihrer ATP-Liste hinzufügen müssen Tresor Links "Nicht umschreiben"- oder URL-Neuschreibungs-Ausnahmeliste von Drittanbietern:

- **Cisco WebEx** `*.webex.com*`
- **Zoomen** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`

Wenn Sie eine vollständige Liste der URLs, die Sie Ihrem ATP hinzufügen möchten Tresor Links "Nicht umschreiben"- oder URL-Neuschreibungsliste von Drittanbietern erhalten möchten, wenden Sie sich an den Drittanbieter für Besprechungsdienste, von dem Sie Besprechungs-Einladungen annehmen möchten. 

> [!CAUTION]
> Fügen Sie Ihrer ATP-Liste nur URLs hinzu, Tresor Links "Nicht umschreiben"- oder URL-Neuschreibungsliste von Drittanbietern.

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>Schritt 3: Aktivieren von Drittanbieterbesprechungen auf Teams-Räume

Der letzte Schritt, den Sie tun müssen, besteht im Teams-Räume Teilnahme an Besprechungen von Drittanbietern. Besprechungen von Drittanbietern benötigen einen Benutzernamen und eine E-Mail-Adresse, um an ihnen teilzunehmen. Wenn sich der Benutzername und die E-Mail-Adresse, die Sie verwenden müssen, vom Raumpostfach des Geräts unterscheiden, müssen Sie sie zu Ihrem Gerät hinzufügen. Dies können Sie in den Teams-Räume oder in der XML-Konfigurationsdatei tun.

### <a name="use-device-settings"></a>Verwenden von Geräteeinstellungen

Wenn Sie Teams-Räume über die Touchscreen-Konsole konfigurieren möchten, gehen Sie wie folgt vor:

1. Wählen Sie Microsoft Teams-Räume Konsole mehr **... aus.**
2. Wählen **Einstellungen** aus, und geben Sie dann den Benutzernamen und das Kennwort für den Geräteadministrator ein.
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

Zum Aktivieren von Zoombesprechungen legen Sie `ZoomMeetingsEnabled` das XML-Element wie folgt auf **True**(wahr) dar.

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
> Um von einem Teams-Räume-Gerät aus an einer Cisco WebEx-Besprechung teilzunehmen, muss die Cisco-Besprechung in WebEx-Besprechungen Pro mithilfe der Cisco WebEx-Webanwendungsversion WBS 40.7 oder höher gehostet werden. 
