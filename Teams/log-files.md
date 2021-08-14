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
description: Hier erhalten Sie Informationen zu von Microsoft Teams erstellten Debug-, Medien- und Desktopprotokollen, wo sie gefunden werden und wie sie bei der Überwachung und Problembehandlung helfen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a39078371ffa30caab6ee43df90bc825c4c081a3
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235320"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Verwenden von Protokolldateien zur Überwachung und Problembehandlung Microsoft Teams

Es gibt drei Arten von Protokolldateien, die vom Client automatisch erstellt werden, und diese können zur Überwachung und Problembehandlung bei Teams:

-   [Debugprotokolle](#debug-logs)

-   [Medienprotokolle](#media-logs)

-   [Desktopprotokolle](#desktop-logs)

In diesem Artikel werden diese Protokolle und ihre Verwendung beschrieben. Informationen zur Problembehandlung für bestimmte Probleme finden Sie unter: [Teams Problembehandlung.](/MicrosoftTeams/troubleshoot/teams) Informationen zum Kontaktieren des Support finden Sie unter [Support erhalten.](/microsoft-365/business-video/get-help-support) Beim Erstellen einer Supportanfrage beim Microsoft-Support benötigt der Supporttechniker die Debugprotokolle. Wenn Sie die Debugprotokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann Microsoft schnell mit der Problembehandlung beginnen. **Medien-** **oder Desktopprotokolle** sind nur erforderlich, wenn sie von Microsoft angefordert werden.

> [!NOTE]
> In diesem Artikel bezieht sich der Begriff **Debugprotokolle** auf die Protokolle, die für die Problembehandlung verwendet werden. Die Dateien, die für diese Protokolle generiert werden, enthalten jedoch den Begriff **Diagnoseprotokolle** in ihren Namen.  

## <a name="collect-and-enable-logging"></a>Erfassen und Aktivieren der Protokollierung

Es ist wichtig, Protokolle zu sammeln, sobald ein Problem auftritt. Die Protokolle können mit nur wenigen Klicks erfasst werden.

Windows: Klicken Sie mit der rechten Maustaste auf das Teams in der Taskleiste, und wählen Sie **Supportdateien sammeln aus.** 

Mac: Wählen Sie das Menü Hilfe und dann **Supportdateien sammeln aus.**

Debug-, Desktop- und Medienprotokolle werden in einem Ordner mit dem Namen MSTeams Diagnostics Log <local data and time> gesammelt. Dieser Ordner kann komprimiert und freigegeben werden, wenn Sie eine Supportanfrage beim Microsoft-Support öffnen. Der Ordner enthält Ordner für Desktop, Besprechung (Medien) und Debuggen (Web). Sie können die Dateien mithilfe der folgenden Tastenkombinationen sammeln:

Windows: STRG+ALT+UMSCHALT+1

Mac: WAHL+BEFEHL+UMSCHALT+1

Die Medienprotokollierung ist standardmäßig deaktiviert. Um die Medienprotokollierung zu aktivieren, müssen Benutzer die Option im Teams aktivieren. Wechseln Sie **zu Einstellungen**  >  **Allgemein**, und wählen Sie Protokollierung für **Besprechungsdiagnose aktivieren (erfordert einen Neustart Teams).** Der Teams muss zum Starten der Protokollierung neu gestartet werden.

> [!NOTE]
> Wenn die Medienprotokollierung aktiviert ist, enthält der Ordner "Besprechung" weitere Dateien, die zum Untersuchen von Audio- und Videoproblemen erforderlich sind. Wenn die Medienprotokollierung nicht aktiviert ist, steht eine begrenzte Anzahl Protokolle zur Verfügung.

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

Anweisungen _zu Ihren Informationen finden Sie_ im Abschnitt Windows und Aktivieren der Protokollierung. Debugprotokolle werden von den Windows- und Mac-Desktopclients sowie von browserbasierten Clients erstellt. Die Protokolle sind textbasierte und werden von unten nach oben gelesen. Sie können mit jedem textbasierten Editor gelesen werden, und beim Anmelden beim Client werden neue Protokolle erstellt.

Debugprotokolle zeigen die folgenden Datenflüsse:

-   Anmeldung

-   Verbindungsanforderungen an Dienste mittlerer Ebene

-   Anruf/Unterhaltung

So sammeln Sie Protokolle für Linux: Tastenkombination: STRG+ALT+UMSCHALT+1 Die Dateien sind in "~/Downloads" verfügbar.

So sammeln Sie Protokolle für den Browser: Tastenkombination: STRG+ALT+UMSCHALT+1 Die Dateien stehen in "%userprofile%\Downloads" zur Verfügung.

## <a name="media-logs"></a>Medienprotokolle

Anweisungen _zu Ihren Informationen finden Sie_ im Abschnitt Windows und Aktivieren der Protokollierung. Medienprotokolle enthalten Diagnosedaten zu Audio, Video und Bildschirmfreigabe in Teams Besprechungen. Sie sind für Supportfälle erforderlich, die mit anrufbezogenen Problemen verknüpft sind.

Die Medienprotokollierung ist standardmäßig deaktiviert. Um Diagnosedaten für Teams zu protokollieren, müssen die Benutzer die Option im Client Teams aktivieren. Wechseln Sie **zu Einstellungen** Allgemein, aktivieren Sie das Kontrollkästchen Protokollierung für die  >   **Besprechungsdiagnose aktivieren (erfordert** einen Neustart von Teams ), starten Sie Teams neu, und reproduzieren Sie das Problem. 

Wenn Sie die Protokolldateien an den Microsoft-Support senden, überprüfen Sie bitte den Zeitstempel der Protokolldateien, um sicherzustellen, dass die Protokolle den Zeitrahmen abdecken, in dem das Problem reproduziert wurde.

So sammeln Sie Protokolle für Linux: Die Dateien sind in ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog und *~/.config/Microsoft/Microsoft Teams/skylib/*.blog verfügbar.

Hier ist eine Liste der generierten Protokolldateien und der Informationen, die sie enthalten.

|Protokolldateiname  |Beschreibung  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Enthält Informationen zum Medienstapel. Dies umfasst den Kanalstatus, z. B. Auflösung, verwendete Decoder und Encoder, die Anzahl der gesendeten und empfangenen Frames sowie den Sitzungsstatus der Kamera- und videobasierten Bildschirmfreigabe (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Zeichnet Informationen im Zusammenhang mit Remotesteuerungsaktionen auf, z. B. den Zeitstempel bei Der Steuerung sowie Mauszeigerinformationen.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Zeichnet Ereignisse der Medienstapelüberwachung auf.         |
|Debug-0-s2790420889.blog    | Enthält Informationen zum Medien-Agent, einschließlich der Qualität des Renderns.          |
|tscalling-0-2061129496.blog   |Zeichnet Ereignisse in der ts-Calling-API auf.       |

## <a name="desktop-logs"></a>Desktopprotokolle

Anweisungen _zu Ihren Informationen finden Sie_ im Abschnitt Windows und Aktivieren der Protokollierung. Desktopprotokolle (auch als Bootstrapperprotokolle bezeichnet) enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser auftreten. Wie medienprotokolle werden diese Protokolle nur benötigt, wenn sie von Microsoft angefordert werden. Die Protokolle sind textbasierte Und können mit jedem textbasierten Editor in einem Top-down-Format gelesen werden.

So sammeln Sie Protokolle für Linux: Klicken Sie auf das symbol Microsoft Teams in der Taskleiste, und wählen Sie **Protokolle erhalten aus.**
Die Dateien sind in ~/.config/Microsoft/Microsoft Teams/logs.txt.  

## <a name="browser-trace"></a>Browser-Ablaufverfolgung

Bei einigen Fehlerkategorien müssen Sie vom Microsoft-Support möglicherweise eine Browser ablaufverfolgung erfassen. Diese Informationen können wichtige Details zum Zustand des Teams, wenn der Fehler auftritt.

Bevor Sie die Browser-Ablaufverfolgung starten, vergewissern Sie sich, dass Sie bei ihrem Teams. Dies ist vor dem Starten der Ablaufverfolgung wichtig, damit die Ablaufverfolgung keine vertraulichen Anmeldeinformationen enthält.

Nachdem Sie sich angemeldet haben, wählen Sie einen der folgenden Links aus, der für Ihren Browser geeignet ist, und führen Sie die angegebenen Schritte aus. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Ersetzen Sie in den Schritten alle Verweise auf das Azure-Portal durch den Teams Client.
  
## <a name="webrtc-logs-in-browsers"></a>WebRTC-Protokolle in Browsern
WebRTC-Protokolle können den Microsoft-Support unterstützen, indem Sie Verbindungsdetails für Audio- und Videoanrufe bereitstellen. Führen Sie die Schritte zum Zugreifen auf die WebRTC-Protokolle in Edge (Chromium) oder Chrome aus: 
  
1.  Öffnen Sie eine neue Registerkarte, und wechseln Sie zu einer der folgenden URLs:
    -   Edge (Chromium): "edge://webrtc-internals/"
    -   Chrome: "chrome://webrtc-internals/"
  
2.  Öffnen Sie die Teams Webanwendung, und reproduzieren Sie das Problem.
  
3.  Wechseln Sie zurück zu der Registerkarte, auf die in Schritt 1 zugegriffen wurde, und es werden mindestens zwei Registerkarten angezeigt:
    -   GetUserMedia-Anforderungen
    -   https://teams.microsoft.com/url

4.  Wählen Sie die Registerkarte mit dem Namen der Teams aus, und speichern Sie den Seiteninhalt.

## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
