---
title: Aktivieren von Teams Rooms-Geräten für die Teilnahme an Besprechungen von Drittanbietern
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
description: In diesem Artikel wird erläutert, wie Sie Ihre Organisation und Teams Rooms-Geräte konfigurieren, um die Teilnahme von Drittanbietern an Cisco WebEx und Zoom zu unterstützen.
ms.openlocfilehash: ac4c57dc5cc743fb7b141ecaaaf3531b35912e77
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997433"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Aktivieren von Teams Room-Geräten für die Teilnahme an Besprechungen von Drittanbietern

Microsoft Teams Rooms-Geräte unterstützen eine One-Touch-Erfahrung für die Teilnahme an Onlinebesprechungen von Drittanbietern, die auch als direkte Gastbesprechung bezeichnet wird. Wenn diese Option aktiviert ist, können Sie mit einem Team Rooms-Gerät an Besprechungen teilnehmen, die auf Cisco WebEx und Zoom gehostet werden, genauso einfach wie an Besprechungen teilnehmen, die in Microsoft Teams gehostet werden.

Bevor Sie von einem Team Rooms-Gerät aus an Besprechungen von Drittanbietern teilnehmen können, müssen Sie die folgenden Schritte tun:

1. Konfigurieren Sie das Exchange Online-Raumpostfach des Teams Rooms-Geräts, um Einladungen zu Besprechungen von Drittanbietern zu verarbeiten.
2. Stellen Sie sicher, dass Ihre Organisation keine Richtlinien hat, die Sie daran hindern würden, eine Verbindung mit Besprechungsdiensten von Drittanbietern zu herstellen.
3. Konfigurieren Sie Ihre Teams Rooms-Geräte so, dass Besprechungen von Drittanbietern zulässig sind.

In den folgenden Abschnitten wird erläutert, wie Sie die einzelnen Schritte ausführen.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Schritt 1: Zulassen der Verarbeitung von Kalenderbesprechungen für Besprechungen von Drittanbietern

Zum Aktivieren einer One-Touch-Join-Erfahrung auf einem Team Rooms-Gerät müssen Sie zuerst die Kalenderverarbeitungsregeln für das Exchange Online-Raumpostfach des Geräts festlegen. Das Raumpostfach muss externe Besprechungen zulassen und den Nachrichtentext und den Betreff behalten, damit die URL angezeigt wird, die für die Teilnahme an der Besprechung eines Drittanbieters erforderlich ist. Gehen Sie wie folgt vor, um diese Optionen für das Raumpostfach mithilfe des [Cmdlets Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) festlegen:

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell herzustellen. Weitere Informationen finden Sie unter Herstellen einer Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) mit Standardauthentifizierung oder Herstellen einer Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)mithilfe der mehrstufigen Authentifizierung , je nach Authentifizierungsmethode.

2. Verwenden Sie den folgenden Befehl, um den Benutzerprinzipalnamen (User Principal Name, UPN) des Raumpostfachs zu erhalten, wenn Sie es nicht kennen:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Suchen Sie den Namen des Raumpostfachs, das Ihrem Team Rooms-Gerät zugeordnet ist, und notieren Sie sich dessen UPN.

4. Nachdem Sie den UPN des Raumpostfachs finden, führen Sie den folgenden Befehl aus. Ersetzen `<UserPrincipalName>` Sie dies durch den UPN des Raumpostfachs:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Weitere Informationen zu [Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Schritt 2: Konfigurieren von Office 365 Threat Protection und Neuschreiben von Links

Um die One-Touch-Join-Erfahrung zu ermöglichen, müssen die Linkinformationen zur Besprechungsbeknüpfung aus der Besprechung eines Drittanbieters in der Besprechungs-Einladung vorhanden und lesbar sein. Wenn Ihre Organisation das [Office 365 Advanced Threat Protection Safe Links-Feature](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) verwendet, oder wenn Sie eine Drittanbieterlösung verwenden, die alle eingehenden und ausgehenden URLs auf Bedrohungen überprüft, kann dies die URLs für die Teilnahme an der Besprechung ändern und die Besprechung vom Gerät "Teams Rooms" unkenntlich machen. Um sicherzustellen, dass dies nicht geschieht, müssen Sie die URLs des Drittanbieter-Besprechungsdiensts der Liste "Sichere Links" von ATP oder der URL des Drittanbieters hinzufügen, um die Ausnahmeliste neu zu schreiben.

Führen Sie die Schritte unter Einrichten einer benutzerdefinierten Liste nicht umschreiben von URLs für sichere Links mithilfe von [ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)aus, um urLs von Drittanbietern zur Liste sicherer Links hinzuzufügen. Wenn Sie eine Drittanbieterlösung verwenden, lesen Sie die Anweisungen für diese Lösung zum Hinzufügen von URLs zur Ausnahmeliste url rewrite.

Im Folgenden finden Sie einige Beispieleinträge, die Sie ihrer LISTE sicherer Links für sichere Links (ATP) möglicherweise hinzufügen müssen, um die Ausnahmeliste "Nicht umschreiben" oder die URL einer Drittanbieter-URL neu zu schreiben:

- **Cisco WebEx**`*.webex.com*`
- **Zoomen** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`

Wenn Sie eine vollständige Liste der URLs, die Sie Ihrer LISTE sicherer Links für sichere Links (ATP) hinzufügen möchten, oder die Url eines Drittanbieters zum Neuschreiben der Ausnahmeliste hinzufügen möchten, wenden Sie sich an den Drittanbieter für Besprechungsdienstanbieter, von dem Sie Besprechungsbesprechungen annehmen möchten. 

> [!CAUTION]
> Fügen Sie nur URLs hinzu, die Sie Ihrer ATP Safe Links-Liste "Nicht neu schreiben" oder der URL eines Drittanbieters vertrauen, die Ausnahmeliste neu schreiben.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Schritt 3: Aktivieren von Drittanbieterbesprechungen auf einem Gerät

Der letzte Schritt, den Sie tun müssen, besteht im Zulassen, dass jedes Team Rooms-Gerät an Besprechungen von Drittanbietern teilnehmen kann. Besprechungen von Drittanbietern erfordern einen Benutzernamen und eine E-Mail-Adresse, um an besprechungen teilzunehmen. Wenn sich der Benutzername und die E-Mail-Adresse, die Sie verwenden müssen, vom Raumpostfach des Geräts unterscheiden, müssen Sie sie Ihrem Gerät hinzufügen. Dies können Sie in den Geräteeinstellungen oder in der XML-Konfigurationsdatei tun.

### <a name="use-device-settings"></a>Verwenden von Geräteeinstellungen

Gehen Sie wie folgt vor, um das Gerät "Teams Rooms" über den Touchscreen zu konfigurieren:

1. Wählen Sie auf dem Microsoft Teams Rooms-Gerät Mehr **... aus.**
2. Wählen **Sie Einstellungen** aus, und geben Sie dann den Benutzernamen und das Kennwort des Geräteadministrators ein.
3. Wechseln Sie zur **Registerkarte Besprechungen,** und wählen **Sie Cisco WebEx,** **Zoom** oder beides aus.
4. Wenn Sie an Besprechungen mit dem Benutzernamen und der E-Mail-Adresse teilnehmen möchten, die dem Raumpostfach zugeordnet sind, wählen Sie **Teilnehmen mit Rauminformationen aus.**
5. Wenn Sie an Besprechungen mit einem alternativen  Benutzernamen und einer alternativen E-Mail-Adresse teilnehmen möchten, wählen Sie Teilnehmen mit benutzerdefinierten Informationen aus, und geben Sie Benutzernamen und E-Mail-Adresse ein, die Sie verwenden möchten.
6. Wählen **Sie Speichern und Beenden aus.** Ihr Gerät wird neu gestartet.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Verwenden der SkypeSettings.xml Konfigurationsdatei

Die folgenden Einstellungen können der Datei hinzugefügt `SkypeSettings.xml` werden, die sich in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` befindet. Weitere Informationen zur Datei finden Sie unter Remoteverwaltung einer Microsoft Teams Rooms-Konsoleneinstellungen `SkypeSettings.xml` mit einer [XML-Konfigurationsdatei.](xml-config-file.md)

Zum Aktivieren von Cisco WebEx-Besprechungen legen Sie das `WebExMeetingsEnabled` XML-Element wie folgt **auf True**(Wahr) vor.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Um Zoombesprechungen zu aktivieren, legen Sie das `ZoomMeetingsEnabled` XML-Element wie folgt **auf True**(Wahr) vor.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Sie können optional einen benutzerdefinierten Benutzernamen und eine benutzerdefinierte E-Mail-Adresse angeben, um an Besprechungen von Drittanbietern mit den folgenden XML-Elementen teilzunehmen. Wenn die von Ihnen angegebenen Werte nicht gültig sind, verwendet das Team Rooms-Gerät standardmäßig den Benutzernamen und die E-Mail-Adresse des Raumpostfachs.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Um von einem Teams Rooms-Gerät aus an einer Cisco WebEx-Besprechung teilnehmen zu können, muss die Cisco-Besprechung mit Cisco WebEx-Webanwendungsversion WBS 40.7 oder höher gehostet werden.
