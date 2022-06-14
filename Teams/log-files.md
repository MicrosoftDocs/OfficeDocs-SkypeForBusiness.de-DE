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
description: Erfahren Sie mehr über Debug-, Medien- und Desktopprotokolle, die von Microsoft Teams erstellt wurden, wo sie gefunden werden können und wie sie bei der Überwachung und Problembehandlung helfen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 178e89ff91de4638f6a9ff56a4dcb935d18f6f91
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056945"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Verwenden von Protokolldateien zum Überwachen und Beheben von Problemen mit Microsoft Teams

Es gibt drei Arten von Protokolldateien, die automatisch vom Client erstellt werden, die verwendet werden können, um die Überwachung und Problembehandlung Teams zu unterstützen:

-   [Debugprotokolle](#debug-logs)

-   [Medienprotokolle](#media-logs)

-   [Desktopprotokolle](#desktop-logs)

In diesem Artikel werden diese Protokolle und deren Verwendung beschrieben. Informationen zur Problembehandlung bei bestimmten Problemen finden Sie [unter: Teams Problembehandlung](/MicrosoftTeams/troubleshoot/teams). Informationen zum Kontaktieren des Supports finden [Sie unter "Support anfordern"](/microsoft-365/business-video/get-help-support). Beim Erstellen einer Supportanfrage mit Microsoft-Support benötigt der Supporttechniker die Debugprotokolle. Wenn Sie die Debugprotokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann Microsoft schnell mit der Problembehandlung beginnen. **Medien** - oder **Desktopprotokolle** sind nur erforderlich, wenn sie von Microsoft angefordert werden.

> [!NOTE]
> In diesem Artikel bezieht sich der Begriff **Debugprotokolle** auf die Protokolle, die für die Problembehandlung verwendet werden. Die Dateien, die für diese Protokolle generiert werden, enthalten jedoch den Begriff **Diagnoseprotokolle** in ihren Namen.  

## <a name="collect-and-enable-logging"></a>Erfassen und Aktivieren der Protokollierung

Es ist wichtig, Protokolle zu sammeln, sobald ein Problem auftritt. Die Protokolle können mit nur wenigen Klicks gesammelt werden.

- Windows: Klicken Sie mit der rechten Maustaste auf das Symbol Teams in der Taskleiste, und wählen Sie **"Supportdateien sammeln"** aus. 

- Mac: Wählen Sie das Menü "Hilfe" und dann **"Supportdateien sammeln"** aus.

Debug-, Desktop- und Medienprotokolle werden in einem Ordner mit dem Namen _MSTeams Diagnostics Log \<local date and time\>_ gesammelt. Dieser Ordner kann komprimiert und freigegeben werden, wenn Sie eine Supportanfrage mit Microsoft-Support öffnen. Der Ordner enthält Ordner für Desktop, Besprechung (Medien) und Debuggen (Web). Sie können die Dateien mithilfe der folgenden Tastenkombinationen sammeln:

- Windows: <kbd>STRG ALT</kbd> + <kbd></kbd> + <kbd>UMSCHALT</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


Die Medienprotokollierung ist standardmäßig nur für einige CPUs aktiviert, die in [Medienprotokollen](#media-logs) beschrieben werden. Andernfalls ist sie standardmäßig deaktiviert. Um die Medienprotokollierung zu aktivieren, müssen Benutzer die Option im Teams-Client aktivieren. Wechseln Sie zu **Einstellungen** >  **General**, und wählen Sie **"Protokollierung für Besprechungsdiagnose aktivieren" aus (erfordert einen Neustart Teams)**. Der Teams-Client muss neu gestartet werden, damit die Protokollierung beginnt (starten Sie ihn neu, indem Sie mit der rechten Maustaste auf das Symbol in Ihrem Dock (Mac) oder der Taskleiste (Windows) klicken und **"Beenden**" auswählen. Klicken Sie nach dem Beenden einfach auf das App-Symbol, um es erneut zu öffnen).

Wenn ein Problem mit einer bestimmten Besprechung oder einem bestimmten Liveereignis auftritt, ist es hilfreich, die URL der Besprechung zugeordnet zu haben. Dadurch werden zusätzliche Informationen bereitgestellt, um das genaue Besprechungs- oder Liveereignis in den Protokollen zu ermitteln. Diese Informationen können von jedem Teilnehmer für eine Besprechung oder von einem Referenten oder Produzenten für ein Liveereignis gesammelt werden. Diese URL kann erfasst werden, indem Sie mit der Maus auf die Verknüpfungs-URL zeigen und " **Link kopieren"** auswählen.

> [!NOTE]
> Wenn die Medienprotokollierung aktiviert ist, sind zusätzliche Dateien im Besprechungsordner enthalten, die zum Untersuchen von Audio- und Videoproblemen erforderlich sind. Wenn die Medienprotokollierung nicht aktiviert ist, ist eine begrenzte Anzahl von Protokollen verfügbar.
  
> [!NOTE]
> Die Debugprotokolle wurden zuvor mithilfe der nachstehenden Tastenkombinationen erfasst. Diese funktionieren weiterhin und führen die gleiche Protokollerfassung wie die Option **"Supportdateien sammeln"** aus.
>
> - Windows<kbd></kbd>: <kbd>ALT-UMSCHALT</kbd> + <kbd></kbd> + <kbd></kbd> + 1
>
> - Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


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

Anweisungen zu Windows und Mac finden Sie im Abschnitt _zum Sammeln und Aktivieren der Protokollierung_. Debugprotokolle werden von den Windows- und Mac-Desktopclients sowie von browserbasierten Clients erstellt. Die Protokolle sind textbasiert und werden von unten nach oben gelesen. Sie können mit jedem textbasierten Editor gelesen werden, und neue Protokolle werden erstellt, wenn Sie sich beim Client anmelden.

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

Anweisungen zu Windows und Mac finden Sie im Abschnitt _zum Sammeln und Aktivieren der Protokollierung_. Medienprotokolle enthalten Diagnosedaten zu Audio, Video und Bildschirmfreigabe in Teams Besprechungen. Sie sind für Supportfälle erforderlich, die mit Anrufproblemen verknüpft sind.

Die Medienprotokollierung ist für Computer standardmäßig aktiviert, wenn Ihre CPU folgende Lautet:
- beliebige Apple M1
- Alle Intel-Xeon-
- intel i9, mit Ausnahme der U-, G7-, M- und MQ-Serie
- intel i7 der 6. Generation und später, mit Ausnahme der U-, G7-, M- und MQ-Serie

Andernfalls ist sie standardmäßig deaktiviert. Um Diagnosedaten für Teams Besprechungen zu protokollieren, müssen Benutzer die Option im Teams-Client aktivieren. Wechseln Sie zu **Einstellungen** >  **General**, aktivieren Sie das Kontrollkästchen **Protokollierung für die Besprechungsdiagnose aktivieren (erfordert einen Neustart Teams**), starten Sie Teams neu, und reproduzieren Sie das Problem. 

> [!NOTE]
> Wenn Sie sich von Teams abmelden, wird die Medienprotokollierung auf den Standardwert zurückgesetzt. 

Wenn Sie die Protokolldateien an den Microsoft-Support senden, überprüfen Sie den Zeitstempel der Protokolldateien, um sicherzustellen, dass die Protokolle den Zeitrahmen abdecken, wenn Sie das Problem reproduziert haben.

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

Anweisungen zu Windows und Mac finden Sie im Abschnitt _zum Sammeln und Aktivieren der Protokollierung_. Desktopprotokolle, auch als Bootstrapper-Protokolle bezeichnet, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser auftreten. Wie Medienprotokolle werden diese Protokolle nur benötigt, wenn sie von Microsoft angefordert werden. Die Protokolle sind textbasiert und können mit jedem textbasierten Editor in einem Top-Down-Format gelesen werden.

So sammeln Sie Protokolle für Linux:
- Klicken Sie auf der Taskleiste auf das Symbol Microsoft Teams, und wählen Sie **"Protokolle abrufen" aus**.
- Die Dateien sind in `~/.config/Microsoft/Microsoft Teams/logs.txt`verfügbar.

So sammeln Sie Protokolle für Mac:
- Klicken Sie in Microsoft Teams auf das Menü "Hilfe", und wählen Sie **"Supportdateien sammeln**" aus.
- Die `logs.txt` Datei befindet sich im Ordner "Desktop" im Ordner _"MSTeams Diagnostics Log" \<local date and time>_ .

So sammeln Sie Protokolle für Windows:
- Klicken Sie auf das Symbol Microsoft Teams in der Taskleiste, und wählen Sie **"Supportdateien sammeln**" aus.
- Die `logs.txt` Datei wird automatisch in Editor geöffnet.

Wenn Sie Probleme beim Anmelden bei Teams untersuchen, müssen Sie die Desktopprotokolle möglicherweise manuell sammeln. Diese Protokolldateien befinden sich unter %appdata%\Microsoft\Teams in Windows.

## <a name="browser-trace"></a>Browserablaufverfolgung

Bei einigen Kategorien von Fehlern müssen Microsoft-Support möglicherweise eine Browserablaufverfolgung sammeln. Diese Informationen können wichtige Details zum Status des Teams Clients liefern, wenn der Fehler auftritt.

Bevor Sie die Browserablaufverfolgung starten, stellen Sie sicher, dass Sie bei Teams angemeldet sind. Dies ist wichtig, bevor Sie die Ablaufverfolgung starten, damit die Ablaufverfolgung keine vertraulichen Anmeldeinformationen enthält.

Nachdem Sie sich angemeldet haben, wählen Sie je nach Browser einen der folgenden Links aus, und führen Sie die angegebenen Schritte aus. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Ersetzen Sie in den Schritten alle Verweise auf die Azure-Portal durch den Teams Client.
  
## <a name="webrtc-logs-in-browsers"></a>WebRTC-Protokolle in Browsern
WebRTC-Protokolle können Microsoft-Support unterstützen, indem Verbindungsdetails für Audio- und Videoanrufe bereitgestellt werden. Führen Sie die Schritte aus, um auf die WebRTC-Protokolle in Edge (Chromium) oder Chrome zuzugreifen: 
  
1.  Öffnen Sie eine neue Registerkarte, und wechseln Sie zu einer der folgenden URLs:
    -   Edge (Chromium):`edge://webrtc-internals/`
    -   Chrome: `chrome://webrtc-internals/`
  
2.  Öffnen Sie die Teams-Webanwendung, und reproduzieren Sie das Problem.
  
3.  Zurück zu der Registerkarte, auf die in Schritt 1 zugegriffen wurde, und es werden mindestens zwei Registerkarten angezeigt:
    -   GetUserMedia-Anforderungen
    -   `https://teams.microsoft.com/url`

4.  Wählen Sie die Registerkarte mit dem Namen der Teams Anwendung aus, und speichern Sie den Seiteninhalt.

## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
