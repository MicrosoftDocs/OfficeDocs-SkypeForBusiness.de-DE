---
title: Konfigurieren von Protokolldateien für die Überwachung und Problembehandlung in Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Erfahren Sie mehr über Debug-, Medien- und Desktopprotokolle, die von Microsoft Teams erstellt wurden, wo sie zu finden sind und wie sie bei der Überwachung und Problembehandlung helfen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2edddca64bf0cb50dc29758fd60bc397cbc00f8b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705814"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>Konfigurieren von Protokolldateien für die Überwachung und Problembehandlung in Teams

Es gibt drei Arten von Protokolldateien, die automatisch vom Client erstellt werden, die zur Unterstützung der Überwachung und Problembehandlung von Teams genutzt werden können:

-   [Debugprotokolle](#debug-logs)

-   [Medienprotokolle](#media-logs)

-   [Desktopprotokolle](#desktop-logs)

In diesem Artikel werden diese Protokolle und deren Verwendung beschrieben. Informationen zur Problembehandlung bei bestimmten Problemen finden Sie unter: [Microsoft Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams). 

Informationen zum Sammeln von Protokollen von Microsoft Teams-Räume Geräten finden [Sie unter Herunterladen von Geräteprotokollen](/microsoftteams/rooms/rooms-manage#download-device-logs).

Informationen zum Kontaktieren des Supports finden [Sie unter "Support anfordern"](/microsoft-365/business-video/get-help-support).

> [!NOTE]
> In diesem Artikel bezieht sich der Begriff **Debugprotokolle** auf die Protokolle, die für die Problembehandlung verwendet werden. Die Dateien, die für diese Protokolle generiert werden, enthalten jedoch den Begriff **Diagnoseprotokolle** in ihren Namen.  

## <a name="logs-overview"></a>Übersicht über Protokolle

Es ist wichtig, Protokolle zu sammeln, sobald ein Problem auftritt.

Beim Erstellen einer Supportanfrage mit Microsoft-Support benötigt der Supporttechniker die Debugprotokolle. Wenn Sie die Debugprotokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann Microsoft schnell mit der Problembehandlung beginnen. **Medien** - oder **Desktopprotokolle** sind nur erforderlich, wenn sie von Microsoft angefordert werden.

Debug-, Desktop- und Medienprotokolle werden in einem Ordner mit dem Namen _MSTeams Diagnostics Log \<local date and time\>_ gesammelt. Dieser Ordner kann komprimiert und freigegeben werden, wenn Sie eine Supportanfrage mit Microsoft-Support öffnen. Der Ordner enthält Ordner für Desktop, Besprechung (Medien) und Debuggen (Web). Sie können die Dateien mithilfe der folgenden Tastenkombinationen sammeln:

- Windows: <kbd>STRG ALT</kbd> + <kbd></kbd> + <kbd>UMSCHALT</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


Wenn ein Problem mit einer bestimmten Besprechung oder einem bestimmten Liveereignis auftritt, ist es hilfreich, die URL der Besprechung zugeordnet zu haben. Die URL stellt zusätzliche Informationen bereit, um das genaue Besprechungs- oder Liveereignis in den Protokollen zu ermitteln. Diese Informationen können von jedem Teilnehmer für eine Besprechung oder von einem Referenten oder Produzenten für ein Liveereignis gesammelt werden. Diese URL kann erfasst werden, indem Sie mit der Maus auf die Verknüpfungs-URL zeigen und " **Link kopieren"** auswählen.

> [!NOTE]
> Wenn die Medienprotokollierung aktiviert ist, sind zusätzliche Dateien im Besprechungsordner enthalten, die zum Untersuchen von Audio- und Videoproblemen erforderlich sind. Wenn die Medienprotokollierung nicht aktiviert ist, ist eine begrenzte Anzahl von Protokollen verfügbar.
  
In der folgenden Tabelle sind die verschiedenen Clients und die zugehörigen Protokolle aufgeführt. Protokolldateien werden an speicherortspezifischen Speicherorten für den Client und das Betriebssystem gespeichert.

|Client |Debug|Desktop|Medien|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Eine vollständige Liste der unterstützten Betriebssysteme und Browser finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).

## <a name="debug-logs"></a>Debugprotokolle

Debugprotokolle werden von den Windows- und Mac-Desktopclients sowie von browserbasierten Clients erstellt. Die Protokolle sind textbasiert und werden von unten nach oben gelesen. Sie können mit jedem textbasierten Editor gelesen werden, und neue Protokolle werden erstellt, wenn Sie sich beim Client anmelden.

Debugprotokolle zeigen die folgenden Datenflüsse:

-   Anmeldung

-   Verbindungsanforderungen an Dienste der mittleren Ebene

-   Anruf/Unterhaltung

So sammeln Sie Protokolle für Linux:
- Tastenkombination: <kbd>STRG ALT</kbd> + <kbd></kbd> + <kbd>UMSCHALT</kbd> + <kbd>1</kbd>  
- Die Dateien sind in `~/Downloads`

So sammeln Sie Protokolle für Browser und Windows:
- Tastenkombination: <kbd>STRG ALT</kbd> + <kbd></kbd> + <kbd>UMSCHALT</kbd> + <kbd>1</kbd>  
- Die Dateien sind in `%userprofile%\Downloads`

So sammeln Sie Protokolle für Mac:
- Tastenkombination: <kbd>Optionsbefehl</kbd> + <kbd></kbd> + <kbd>Umschalt</kbd> + <kbd>1</kbd>  
- Die Dateien sind in `~/Downloads`

## <a name="media-logs"></a>Medienprotokolle

Medienprotokolle enthalten Diagnosedaten zur Audio-, Video- und Bildschirmfreigabe in Teams-Besprechungen. Sie sind für Supportfälle erforderlich, die mit Anrufproblemen verknüpft sind.

Die Medienprotokollierung ist für Computer standardmäßig aktiviert, wenn Ihre CPU folgende Lautet:
- beliebige Apple M1
- Alle Intel-Xeon-
- intel i9, mit Ausnahme der U-, G7-, M- und MQ-Serie
- intel i7 der 6. Generation und später, mit Ausnahme der U-, G7-, M- und MQ-Serie

Andernfalls ist sie standardmäßig deaktiviert. Es gibt zwei Möglichkeiten zum Protokollieren von Diagnosedaten für Teams-Besprechungen:

- Admin-Konfiguration– Sie können Medienprotokolle für Ihre Endbenutzer verwalten
- Endbenutzerkonfiguration: Ihre Endbenutzer können Medienprotokolle aktivieren

### <a name="admin-configuration"></a>Admin-Konfiguration

Die Verwaltung von Medienprotokollen für Ihre Endbenutzer bietet eine nahtlose Problembehandlung, insbesondere bei zeitweilig auftretenden Problemen. Administratoren können das Cmdlet "TeamsMediaLoggingPolicy" verwenden, um die Medienprotokollierung für Benutzer zu aktivieren und zu verwalten.

Lesen Sie [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) für PowerShell-Cmdlets und weitere Informationen.

### <a name="end-user-configuration"></a>Endbenutzerkonfiguration

Damit Ihre Endbenutzer Diagnosedaten für Teams-Besprechungen protokollieren können, müssen sie die Option im Teams-Client aktivieren. Sie wechseln zu **"Einstellungen** > **allgemein**", aktivieren das Kontrollkästchen " **Medienprotokolle aktivieren" (Diagnosedaten für Audio, Video und Bildschirmfreigabe),** und reproduzieren das Problem.

> [!NOTE]
> Wenn sich Ihre Benutzer von Teams abmelden, wird die Medienprotokollierung auf den Standardwert zurückgesetzt.

### <a name="collecting-and-sending-media-logs"></a>Sammeln und Senden von Medienprotokollen

Bevor Sie die Protokolldateien an den Microsoft-Support senden, überprüfen Sie den Zeitstempel der Protokolldateien, um sicherzustellen, dass die Protokolle den Zeitrahmen abdecken, wenn Sie das Problem reproduziert haben.

So sammeln Sie Protokolle für Linux:  
- Die Dateien sind an den folgenden Speicherorten verfügbar:
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

So sammeln Sie Protokolle für Windows:  
- Die Dateien sind an den folgenden Speicherorten verfügbar:
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

So sammeln Sie Protokolle für Mac:
- Die Dateien sind an den folgenden Speicherorten verfügbar:
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

Hier ist eine Liste der generierten Protokolldateien und der darin enthaltenen Informationen.

<br/>

|Protokolldateiname  |Beschreibung  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | Enthält Informationen zum Medienstapel. Dies umfasst den Kanalstatus wie Auflösung, verwendete Decoder und Encoder, die Anzahl der gesendeten und empfangenen Frames sowie den Sitzungsstatus der Kamera- und Video-basierten Bildschirmfreigabe (VBSS).         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |Zeichnet Informationen im Zusammenhang mit Remotesteuerungsaktionen auf, z. B. den Zeitstempel, wenn die Steuerung angegeben wird, und Mauszeigerinformationen.          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |Zeichnet Medienstapelüberwachungsereignisse auf.         |
|`Debug-0-s2790420889.blog`    | Enthält Informationen zum Medien-Agent, einschließlich der Renderingqualität.          |
|`tscalling-0-2061129496.blog`   |Zeichnet Ereignisse in der ts-calling-API auf.       |

## <a name="desktop-logs"></a>Desktopprotokolle

Desktopprotokolle, auch als Bootstrapper-Protokolle bezeichnet, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser auftreten. Wie Medienprotokolle werden diese Protokolle nur benötigt, wenn sie von Microsoft angefordert werden. Die Protokolle sind textbasiert und können mit jedem textbasierten Editor in einem Top-Down-Format gelesen werden.

So sammeln Sie Protokolle für Linux:
- Klicken Sie auf das Microsoft Teams-Symbol in Ihrer Taskleiste, und wählen Sie **"Protokolle abrufen" aus**.
- Die Dateien sind in `~/.config/Microsoft/Microsoft Teams/logs.txt`verfügbar.

So sammeln Sie Protokolle für Mac:
- Klicken Sie in Microsoft Teams auf das Menü "Hilfe", und wählen Sie **"Supportdateien sammeln"** aus.
- Die `logs.txt` Datei befindet sich im Ordner "Desktop" im Ordner _"MSTeams Diagnostics Log" \<local date and time>_ .

So sammeln Sie Protokolle für Windows:
- Klicken Sie auf das Microsoft Teams-Symbol in Ihrer Taskleiste, und wählen Sie **"Supportdateien sammeln**" aus.
- Die `logs.txt` Datei wird automatisch im Editor geöffnet.

Wenn Sie Probleme beim Anmelden bei Teams untersuchen, müssen Sie die Desktopprotokolle möglicherweise manuell sammeln. Diese Protokolldateien befinden sich unter %appdata%\Microsoft\Teams in Windows.

## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)

[Browserprotokolle und Ablaufverfolgung für Teams](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
