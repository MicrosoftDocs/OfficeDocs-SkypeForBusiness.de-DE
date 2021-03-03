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
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761093"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
=================================================

Es gibt drei Arten von Protokolldateien, die vom Client automatisch erstellt werden, die zur Unterstützung bei der Problembehandlung von Microsoft Teams genutzt werden können:

-   Debugprotokolle

-   Medienprotokolle

-   Desktopprotokolle

Beim Erstellen einer Supportanfrage beim Microsoft-Support erfordert der Supporttechniker die Debug-Protokolle. Nachdem die Debug-Protokolle zur Hand sind, bevor die Support-Anforderung erstellt wird, kann Microsoft schnell mit der Problembehandlung beginnen. **Medien** -oder **Desktop** Protokolle sind nur erforderlich, wenn Sie von Microsoft angefordert werden.

> [!NOTE]
> In diesem Artikel bezieht sich der Begriff **Debug-Protokolle** auf die Protokolle, die für die Problembehandlung verwendet werden. Die Dateien, die für diese Protokolle generiert werden, enthalten jedoch den Begriff **Diagnoseprotokolle** in ihren Namen.  

In der folgenden Tabelle werden die verschiedenen Clients und die zugehörigen Protokolle erläutert. Protokolldateien werden an Speicherorten gespeichert, die für Client und betriebssystemspezifisch sind.


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

Dies sind die am häufigsten verwendeten Protokolle, die für alle Microsoft-Supportfälle erforderlich sind. Debug-Protokolle werden von den Windows-und Mac-Desktop Clients sowie von browserbasierten Clients erstellt. Die Protokolle sind Text basiert und werden von unten nach oben gelesen. Sie können mithilfe eines beliebigen textbasierten Editors gelesen und neue Protokolle erstellt werden, wenn Sie sich beim Client anmelden.

Debugprotokolle zeigen die folgenden Datenflüsse:

-   Anmeldung

-   Verbindungsanforderungen an Dienste mittlerer Ebene

-   Anruf/Unterhaltung

Die Debug-Protokolle werden mithilfe der folgenden betriebssystemspezifischen Methoden erstellt:

-   Windows:

      Tastenkombination: STRG+ALT+UMSCHALT+1

-   Mac OSX:

      Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1

-   Linux

      Tastenkombination: STRG+ALT+UMSCHALT+1

Die Debug-Protokolle werden automatisch in die folgenden Ordner heruntergeladen:

-   Windows: %userprofile%\\Downloads

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert

<a name="media-logs"></a>Medienprotokolle
---------------------------

Medienprotokolle enthalten diagnostische Daten zur Audio-, Video-und Bildschirmfreigabe in Teams-Besprechungen. Sie sind für Supportfälle erforderlich, die mit anrufbezogenen Problemen verknüpft sind.

Die Medien Protokollierung ist standardmäßig deaktiviert. Zum Protokollieren von Diagnosedaten für Teams-Besprechungen müssen die Benutzer die Option im Teams-Client aktivieren. Wechseln Sie zu **Einstellungen**  >  **Allgemein**, aktivieren Sie das Kontrollkästchen **Protokollierung für die Besprechungs Diagnose aktivieren (erfordert einen Neustart von Teams**), starten Sie Teams neu, und reproduzieren Sie das Problem. 

In der folgenden Tabelle werden die Speicherorte des Medien Protokolls erläutert. Wenn Sie die Protokolldateien an den Microsoft-Support senden, überprüfen Sie bitte den Zeitstempel der Protokolldateien, um sicherzustellen, dass die Protokolle den Zeitrahmen abdecken, wenn Sie das Problem reproduzieren.

|Client |Speicherort |
|---------|---------|
|Windows     |%APPDATA%\Microsoft\Teams\media-Stack \\ *. Blog         |
|            |%APPDATA%\Microsoft\Teams\skylib \\ *. Blog
|            |%APPDATA%\Microsoft\Teams\media-Stack \\ *. ETL         |
|Mac OSX     |~/Library/Application-Unterstützung/Microsoft/Teams/Media-Stack/*. Blog         |
|            |~/Library/Application-Unterstützung/Microsoft/Teams/skylib/*. Blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/Media-Stack/*. Blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*. Blog         |

Nachfolgend finden Sie eine Liste der generierten Protokolldateien und der darin enthaltenen Informationen.

|Name der Protokolldatei  |Beschreibung  |
|---------|---------|
|Teams. msrtc-0-s1039525249. Blog     | Enthält Informationen im Zusammenhang mit dem Medien Stapel. Dazu gehören Kanalstatus wie Auflösung, verwendete Decoder und Encoder sowie die Anzahl der gesendeten und empfangenen Frames sowie der Kamera-und videobasierte schlechte VBSS-Sitzungsstatus (Screen Sharing).         |
|rtmcontrol. msrtc-0-2415069487. Blog      |Zeichnet Informationen zu Remote Steuerungsaktionen auf, beispielsweise den Zeitstempel, wenn das Steuerelement angegeben wird, und Mauszeiger Informationen.          |
|Teams_MediaStackETW -2-u-XR-u. ETL      |Zeichnet Medien Stapel-Ablaufverfolgungsereignisse auf.         |
|Debug-0-s2790420889. Blog    | Enthält Informationen zum Medien Agenten, einschließlich der Rendering-Qualität.          |
|tscalling-0-2061129496. Blog   |Zeichnet Ereignisse in der TS-Aufruf-API auf.       |

<a name="desktop-logs"></a>Desktopprotokolle
---------------------

Desktop Protokolle, auch als Bootstrapper-Protokolle bezeichnet, enthalten Protokolldaten, die zwischen dem Desktop Client und dem Browser erfolgen. Wie Medienprotokolle werden diese Protokolle nur benötigt, wenn Sie von Microsoft angefordert werden. Die Protokolle sind Text basiert und können mithilfe eines beliebigen textbasierten Editors in einem Top-Down-Format gelesen werden.

Windows:

 - Klicken Sie mit der rechten Maustaste auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.

Mac OSX:

 - Wählen Sie im Pulldown-Menü **Hilfe** die Option **Protokolle abrufen** aus.

Linux

 - Klicken Sie in der Taskleiste auf das **Microsoft Teams** -Symbol, und wählen Sie **Protokolle abrufen** aus.

|Client |Speicherort |
|---------|---------|
|Windows     |% APPDATA% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application-Unterstützung/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
