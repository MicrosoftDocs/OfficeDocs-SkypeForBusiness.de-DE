---
title: Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
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
description: Erfahren Sie mehr über die von Microsoft Teams erstellten Debug-, Medien- und Desktopprotokolle, wo sie gefunden werden und wie sie bei der Überwachung und Problembehandlung helfen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337742"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Verwenden von Protokolldateien zur Überwachung und Problembehandlung Microsoft Teams

Es gibt drei Arten von Protokolldateien, die vom Client automatisch erstellt werden, und diese können zur Unterstützung bei der Überwachung und Problembehandlung bei Teams:

-   [Debugprotokolle](#debug-logs)

-   [Medienprotokolle](#media-logs)

-   [Desktopprotokolle](#desktop-logs)

In diesem Artikel werden die drei Protokolle und ihre Verwendung beschrieben. 

Informationen zur Problembehandlung bei bestimmten Problemen finden Sie unter: [Teams Problembehandlung.](/MicrosoftTeams/troubleshoot/teams) Informationen zum Kontaktieren des Support finden Sie unter [Support erhalten.](/microsoft-365/business-video/get-help-support)

Beim Erstellen einer Supportanfrage beim Microsoft-Support benötigt der Supporttechniker die Debugprotokolle. Wenn Sie die Debugprotokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann Microsoft schnell mit der Problembehandlung beginnen. **Medien-** **oder Desktopprotokolle** sind nur erforderlich, wenn sie von Microsoft angefordert werden.

> [!NOTE]
> In diesem Artikel bezieht sich der Begriff **Debugprotokolle** auf die Protokolle, die für die Problembehandlung verwendet werden. Die Dateien, die für diese Protokolle generiert werden, enthalten jedoch den Begriff **Diagnoseprotokolle** in ihren Namen.  

In der folgenden Tabelle sind die verschiedenen Clients und die zugehörigen Protokolle aufgeführt. Protokolldateien werden an Speicherorten gespeichert, die für den Client und das Betriebssystem spezifisch sind.


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

Dies sind die am häufigsten verwendeten Protokolle, die für alle Microsoft-Supportfälle erforderlich sind. Debugprotokolle werden von den Windows- und Mac-Desktopclients sowie von browserbasierten Clients erstellt. Die Protokolle sind textbasierte und werden von unten nach oben gelesen. Sie können mit jedem textbasierten Editor gelesen werden, und beim Anmelden beim Client werden neue Protokolle erstellt.

Debugprotokolle zeigen die folgenden Datenflüsse:

-   Anmeldung

-   Verbindungsanforderungen an Dienste mittlerer Ebene

-   Anruf/Unterhaltung

Die Debugprotokolle werden mit den folgenden osspezifischen Methoden erstellt:

-   Windows:

      Tastenkombination: STRG+ALT+UMSCHALT+1

-   Mac OSX:

      Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1

-   Linux:

      Tastenkombination: STRG+ALT+UMSCHALT+1

Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen:

-   Windows: %userprofile%\\Downloads

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert

## <a name="media-logs"></a>Medienprotokolle

Medienprotokolle enthalten Diagnosedaten zu Audio, Video und Bildschirmfreigabe in Teams Besprechungen. Sie sind für Supportfälle erforderlich, die mit anrufbezogenen Problemen verknüpft sind.

Die Medienprotokollierung ist standardmäßig deaktiviert. Um Diagnosedaten für Teams zu protokollieren, müssen die Benutzer die Option im Client Teams aktivieren. Wechseln Sie **zu Einstellungen** Allgemein, aktivieren Sie das Kontrollkästchen Protokollierung für die  >   **Besprechungsdiagnose aktivieren (erfordert** einen Neustart von Teams ), starten Sie Teams neu, und reproduzieren Sie das Problem. 

In der folgenden Tabelle werden die Speicherorte des Medienprotokolls skizziert. Wenn Sie die Protokolldateien an den Microsoft-Support senden, überprüfen Sie bitte den Zeitstempel der Protokolldateien, um sicherzustellen, dass die Protokolle den Zeitrahmen abdecken, in dem das Problem reproduziert wurde.

|Client |Speicherort |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

Hier ist eine Liste der generierten Protokolldateien und der Informationen, die sie enthalten.

|Protokolldateiname  |Beschreibung  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Enthält Informationen zum Medienstapel. Dies umfasst den Kanalstatus, z. B. Auflösung, verwendete Decoder und Encoder, die Anzahl der gesendeten und empfangenen Frames sowie den Sitzungsstatus der Kamera- und videobasierten Bildschirmfreigabe (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Zeichnet Informationen im Zusammenhang mit Remotesteuerungsaktionen auf, z. B. den Zeitstempel bei Der Steuerung sowie Mauszeigerinformationen.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Zeichnet Ereignisse der Medienstapelüberwachung auf.         |
|Debug-0-s2790420889.blog    | Enthält Informationen zum Medien-Agent, einschließlich der Qualität des Renderns.          |
|tscalling-0-2061129496.blog   |Zeichnet Ereignisse in der ts-Calling-API auf.       |

## <a name="desktop-logs"></a>Desktopprotokolle

Desktopprotokolle (auch als Bootstrapperprotokolle bezeichnet) enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser auftreten. Wie Medienprotokolle werden diese Protokolle nur benötigt, wenn sie von Microsoft angefordert werden. Die Protokolle sind textbasierte Und können mit jedem textbasierten Editor in einem Top-down-Format gelesen werden.

Windows:

 - Klicken Sie mit der rechten **Maustaste Microsoft Teams** auf das Symbol "Protokoll" in der Taskleiste, und wählen Sie Protokolle **erhalten aus.**

Mac OsX:

 - Wählen Sie im Pull-down-Menü Hilfe die Option Protokolle erhalten aus.  

Linux:

 - Klicken Sie auf **das Microsoft Teams** in der Taskleiste, und wählen Sie Protokolle **erhalten aus.**

|Client |Speicherort |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="browser-trace"></a>Browser-Ablaufverfolgung

Bei einigen Fehlerkategorien müssen Sie vom Microsoft-Support möglicherweise eine Browser ablaufverfolgung erfassen. Diese Informationen können wichtige Details zum Zustand des Teams, wenn der Fehler auftritt.

Bevor Sie die Browser-Ablaufverfolgung starten, vergewissern Sie sich, dass Sie bei ihrem Teams. Dieser Schritt ist vor dem Starten der Ablaufverfolgung wichtig, damit die Ablaufverfolgung keine vertraulichen Anmeldeinformationen enthält.

Nachdem Sie sich angemeldet haben, wählen Sie einen der folgenden Links aus, der für Ihren Browser geeignet ist, und führen Sie die angegebenen Schritte aus. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Ersetzen Sie in den Schritten alle Verweise auf das Azure-Portal durch den Teams Client. 

## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
