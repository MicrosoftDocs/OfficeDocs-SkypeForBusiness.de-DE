---
title: Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Hier erhalten Sie Informationen zu den von Microsoft Teams erstellten Debug-, Medien- und Desktopprotokollen, zu deren Speicherort und wie diese für die Problembehandlung eingesetzt werden können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112191"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
=================================================

Es gibt drei Typen von Protokolldateien, die vom Client automatisch erstellt werden, die zur Unterstützung bei der Problembehandlung von Microsoft Teams verwendet werden können:

-   Debugprotokolle

-   Medienprotokolle

-   Desktopprotokolle

Beim Erstellen einer Supportanfrage mit dem Microsoft-Support benötigt der Supporttechniker die Debugprotokolle. Wenn Sie die Debugprotokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann Microsoft schnell mit der Problembehandlung beginnen. **Medien-** **oder Desktopprotokolle** sind nur erforderlich, wenn sie von Microsoft angefordert werden.

> [!NOTE]
> In diesem Artikel bezieht sich der Begriff **Debugprotokolle** auf die Protokolle, die zur Problembehandlung verwendet werden. Die dateien, die für diese Protokolle generiert werden, enthalten jedoch den Begriff **Diagnoseprotokolle** in ihren Namen.  

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

<a name="debug-logs"></a>Debugprotokolle
---------------------------

Dies sind die am häufigsten verwendeten Protokolle, die für alle Microsoft-Supportfälle erforderlich sind. Debugprotokolle werden von den Windows- und Mac-Desktopclients sowie von browserbasierten Clients erstellt. Die Protokolle sind textbasierter Text und werden von unten nach oben gelesen. Sie können mit jedem textbasierten Editor gelesen werden, und neue Protokolle werden erstellt, wenn Sie sich beim Client anmelden.

Debugprotokolle zeigen die folgenden Datenflüsse:

-   Anmeldung

-   Verbindungsanforderungen an Dienste der mittleren Ebene

-   Anruf/Unterhaltung

Die Debugprotokolle werden mit den folgenden betriebssystemspezifischen Methoden erstellt:

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

<a name="media-logs"></a>Medienprotokolle
---------------------------

Medienprotokolle enthalten Diagnosedaten zu Audio, Video und Bildschirmfreigabe in Teams-Besprechungen. Sie sind für Supportfälle erforderlich, die mit anrufbezogenen Problemen verknüpft sind.

Die Medienprotokollierung ist standardmäßig deaktiviert. Um Diagnosedaten für Teams-Besprechungen zu protokollieren, müssen Benutzer die Option im Teams-Client aktivieren. Wechseln Sie **zu Einstellungen** Allgemein, aktivieren Sie das Kontrollkästchen Protokollierung für Besprechungsdiagnose aktivieren (erfordert einen Neustart von Teams), starten Sie Teams neu, und  >  reproduzieren Sie das Problem.  

In der folgenden Tabelle sind die Medienprotokollpositionen aufgeführt. Wenn Sie die Protokolldateien an den Microsoft-Support senden, überprüfen Sie bitte den Zeitstempel der Protokolldateien, um sicherzustellen, dass die Protokolle den Zeitrahmen abdecken, wenn Sie das Problem reproduziert haben.

|Client |Speicherort |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

Hier ist eine Liste der generierten Protokolldateien und der informationen, die sie enthalten.

|Protokolldateiname  |Beschreibung  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Enthält Informationen im Zusammenhang mit dem Medienstapel. Dies umfasst Kanalstatus wie Auflösung, verwendete Decoder und Encoder, die Anzahl der gesendeten und empfangenen Frames sowie den Sitzungsstatus der Kamera- und videobasierten Bildschirmfreigabe (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Zeichnet Informationen im Zusammenhang mit Remotesteuerungsaktionen auf, z. B. den Zeitstempel, wenn das Steuerelement angegeben wird, und Mauszeigerinformationen.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Zeichnet Medienstapelverfolgungsereignisse auf.         |
|Debug-0-s2790420889.blog    | Enthält Informationen im Zusammenhang mit dem Medien-Agent, einschließlich der Renderqualität.          |
|tscalling-0-2061129496.blog   |Zeichnet Ereignisse in der ts-calling-API auf.       |

<a name="desktop-logs"></a>Desktopprotokolle
---------------------

Desktopprotokolle, auch als Bootstrapperprotokolle bezeichnet, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser auftreten. Wie Medienprotokolle werden diese Protokolle nur benötigt, wenn sie von Microsoft angefordert werden. Die Protokolle sind textbasierter Text und können mit jedem textbasierten Editor in einem Top-Down-Format gelesen werden.

Windows:

 - Klicken Sie in der Taskleiste **mit der rechten** Maustaste auf das Microsoft Teams-Symbol, und wählen Sie **Protokolle erhalten aus.**

Mac OsX:

 - Wählen **Sie im** Pull-Down-Menü **hilfe** die Option Protokolle erhalten aus.

Linux:

 - Klicken Sie auf **das Microsoft Teams-Symbol** in der Taskleiste, und wählen Sie **Protokolle erhalten aus.**

|Client |Speicherort |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)