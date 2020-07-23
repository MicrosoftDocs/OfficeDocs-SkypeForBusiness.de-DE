---
title: Aktivieren von "Teams Rooms"-Geräten für die Teilnahme an Besprechungen von Drittanbietern
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
description: In diesem Artikel wird beschrieben, wie Sie Ihre Organisations-und teamsräume-Geräte für die Unterstützung von Besprechungen von Drittanbietern in Cisco WebEx und Zoom konfigurieren.
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372214"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Aktivieren von Team Room-Geräten für die Teilnahme an Besprechungen von Drittanbietern

Microsoft Teams rooms-Geräte unterstützen ein einmaliges Erlebnis für die Teilnahme an Onlinebesprechungen von Drittanbietern. Wenn diese Option aktiviert ist, können Sie ein Gerät für teamsräume verwenden, um an Besprechungen teilzunehmen, die auf Cisco WebEx und Zoom<sup>1</sup> gehostet werden, genauso einfach wie Sie an Besprechungen teilnehmen, die in Microsoft Teams gehostet werden.

Bevor Sie von einem Team Room-Gerät an Drittanbieter Besprechungen teilnehmen können, müssen Sie die folgenden Schritte ausführen:

1. Konfigurieren des Exchange Online Room-Postfachs des Teams rooms für die Verarbeitung von Einladungen für Besprechungen von Drittanbietern
2. Stellen Sie sicher, dass Ihre Organisation keine Richtlinien enthält, die verhindern, dass Sie eine Verbindung mit den Besprechungs Diensten von Drittanbietern herstellen.
3. Konfigurieren Sie Ihre Teams rooms-Geräte, um Besprechungen von Drittanbietern zu ermöglichen.

In den folgenden Abschnitten wird erläutert, wie Sie die einzelnen Schritte ausführen.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Schritt 1: genehmigen der Kalender Einladungs Verarbeitung für Besprechungen von Drittanbietern

Das erste, was Sie tun müssen, um ein One-Touch-Join-Erlebnis von einem Team Room-Gerät zu aktivieren, ist die Kalender Verarbeitungsregeln für das Exchange Online Room-Postfach des Geräts festzulegen. Das Raumpostfach muss externe Besprechungen zulassen und den Nachrichtentext und das Thema beibehalten, damit die URL angezeigt wird, die für die Teilnahme an der Besprechung des Drittanbieters erforderlich ist. Gehen Sie wie folgt vor, um diese Raum Postfachoptionen mit dem Cmdlet " [CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) " zu definieren:

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell mit Standardauthentifizierung](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) oder [Herstellen einer Verbindung mit Exchange Online PowerShell mithilfe der mehr](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)stufigen Authentifizierung, je nach Ihrer Authentifizierungsmethode.

2. Rufen Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Room-Postfachs ab, wenn Sie ihn nicht kennen, indem Sie den folgenden Befehl ausführen:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. Suchen Sie den Namen des Raumpostfachs, das mit dem Gerät Ihres Teams rooms verknüpft ist, und notieren Sie sich dessen UPN.

4. Nachdem Sie den UPN des Room-Postfachs gefunden haben, führen Sie den folgenden Befehl aus. Ersetzen Sie dies `<UserPrincipalName>` durch den UPN des Room-Postfachs:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Weitere Informationen zu [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Schritt 2: Konfigurieren von Office 365-Bedrohungsschutz und erneutem Erstellen von Links

Zum Aktivieren der einmaligen Verknüpfungsfunktion müssen Besprechungs Verknüpfungsinformationen aus der Drittanbieter Besprechung in der Besprechungseinladung vorhanden und lesbar sein. Wenn in Ihrer Organisation das Feature " [Erweiterter Bedrohungsschutz" von Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)verwendet   wird oder wenn Sie eine Lösung eines Drittanbieters verwenden, die alle eingehenden und ausgehenden URLs auf Bedrohungen scannt, kann Sie die URLs der Besprechungsteilnahme ändern und die Besprechung vom Gerät "Teams Rooms" unkenntlich machen. Um sicherzustellen, dass dies nicht der Fall ist, müssen Sie die URLs des Drittanbieters des Besprechungs Diensts der ATP-Liste der sicheren Links "nicht umschreiben" oder der Ausnahmeliste für URL-Umschreibungen von Drittanbietern hinzufügen.

Zum Hinzufügen von Drittanbieter-Besprechungs Dienst-URLs zu den ATP-Sicherheits Links "nicht umschreiben" führen Sie die Schritte unter [Einrichten einer benutzerdefinierten URL-Liste "nicht umschreiben" mithilfe von ATP-Sicherheits Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)aus. Wenn Sie eine Lösung eines Drittanbieters verwenden, lesen Sie die Anweisungen für diese Lösung, um URLs zur Ausnahmeliste für URL-Umschreibungen hinzuzufügen.

Nachfolgend sind einige Beispieleinträge aufgeführt, die Sie möglicherweise zu ihren ATP-Sicherheits Links "nicht umschreiben" oder der Ausnahmeliste für URL-Umschreibungen von Drittanbietern hinzufügen müssen:

- **Cisco WebEx**`*.webex.com*`
- **Zoom** `*zoom.us*` , `*zoom.com*` ,`*zoomgov.com*`

Eine vollständige Liste der URLs, die Sie zu ihren ATP-sicheren Links "nicht umschreiben"-Liste oder zur Ausnahmeliste eines Drittanbieters für URL-Umschreibungen hinzufügen können, erhalten Sie vom Drittanbieter-Besprechungs Dienstanbieter, von dem Sie Besprechungseinladungen annehmen möchten. 

> [!CAUTION]
> Fügen Sie nur URLs, denen Sie Vertrauen, zu ihren ATP-sicheren Links "nicht umschreiben"-Liste oder Ausnahmeliste für URL-Umschreibungen von Drittanbietern hinzu.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Schritt 3: Aktivieren von Besprechungen von Drittanbietern auf einem Gerät

Der letzte Schritt besteht darin, das Gerät für die einzelnen Teams für die Teilnahme an Besprechungen von Drittanbietern zu ermöglichen. Für Besprechungen von Drittanbietern müssen Sie einen Benutzernamen und eine e-Mail-Adresse angeben. Wenn der Benutzername und die e-Mail-Adresse, die Sie verwenden müssen, anders als das Raumpostfach des Geräts sind, müssen Sie Sie auf Ihrem Gerät hinzufügen. Dies können Sie in den Geräteeinstellungen oder in der XML-Konfigurationsdatei vornehmen.

### <a name="use-device-settings"></a>Verwenden von Geräteeinstellungen

Gehen Sie wie folgt vor, um das Gerät "Teams Rooms" über seinen Touchscreen zu konfigurieren:

1. Wählen Sie auf dem Gerät Microsoft Teams rooms den Eintrag **mehr...**
2. Wählen Sie **Einstellungen**aus, und geben Sie dann den Benutzernamen und das Kennwort für den Geräteadministrator ein.
3. Wechseln Sie zur Registerkarte **Besprechungen**   , und wählen Sie **Cisco WebEx**, **Zoom**<sup>1</sup>oder beides aus.
4. Wenn Sie mit dem Benutzernamen und der e-Mail-Adresse, die dem Raumpostfach zugeordnet ist, an Besprechungen teilnehmen möchten, wählen Sie **mit Rauminformationen beitreten** aus.
5. Wenn Sie mit einem alternativen Benutzernamen und einer e-Mail-Adresse an Besprechungen teilnehmen möchten, wählen Sie **mit benutzerdefinierten Informationen beitreten** aus, und geben Sie den Benutzernamen und die e-Mail-Adresse ein.
6. Wählen Sie **Speichern und beenden**aus. Ihr Gerät wird neu gestartet.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Verwenden der SkypeSettings.xml-Konfigurationsdatei

Die folgenden Einstellungen können zu der Datei hinzugefügt werden, die `SkypeSettings.xml` sich in befindet `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Weitere Informationen zur `SkypeSettings.xml` Datei finden Sie unter [Verwalten von Microsoft Teams rooms-Konsoleneinstellungen Remote mit einer XML-Konfigurationsdatei](xml-config-file.md).

Um Cisco WebEx-Besprechungen zu aktivieren, `WebExMeetingsEnabled` müssen Sie das XML-Element wie folgt auf " **true**" festlegen.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Um Zoom<sup>1</sup> -Besprechungen zu aktivieren, `ZoomMeetingsEnabled` müssen Sie das XML-Element wie folgt auf " **true**" festlegen.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Optional können Sie einen benutzerdefinierten Benutzernamen und eine e-Mail-Adresse angeben, um mit den folgenden XML-Elementen an Besprechungen von Drittanbietern teilzunehmen. Wenn die von Ihnen bereitgestellten Werte nicht gültig sind, verwendet das Gerät "Teams Rooms" standardmäßig den Benutzernamen und die e-Mail-Adresse für Room Mailbox.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Wenn Sie von einem Team Room-Gerät aus an Cisco WebEx-Besprechung teilnehmen möchten, muss die Cisco-Besprechung mit der Cisco WebEx Web Application-Version PSP 40,7 oder höher gehostet werden.

<sup>1</sup> Zoom-Besprechungsteilnahme ist derzeit nur verfügbar, um Microsoft Teams rooms-Kunden über das Technologie Zugriffs Programm auszuwählen (tippen).
