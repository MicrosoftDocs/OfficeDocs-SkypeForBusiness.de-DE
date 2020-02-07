---
title: Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 2c8da7e60e785d765e77e17935b60382e864a83b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833375"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
=================================================

Es gibt drei Typen von automatisch vom Client erstellten Protokolldateien, die zur Problembehandlung in Microsoft Teams eingesetzt werden können.

-   Debugprotokolle

-   Medienprotokolle

-   Desktopprotokolle

Beim Erstellen einer Supportanfrage beim Microsoft-Support fordert Sie der Supportmitarbeiter zur Einreichung von Debugprotokollen auf. Wenn Sie diese Protokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann das Problem von Microsoft schneller behoben werden. Medien- oder Desktopprotokolle werden nur auf Anforderung von Microsoft benötigt.

In der folgenden Tabelle werden verschiedene Clients und die jeweils zugehörigen Protokolle aufgeführt. Protokolldateien sind in den für den Client und das Betriebssystem spezifischen Verzeichnissen gespeichert.


|Client |Debug|Desktop|Medien|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Eine vollständige Liste der unterstützten Betriebssysteme und Browser finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).

<a name="debug-logs"></a>Debugprotokolle
---------------------------

Dies sind die am häufigsten verwendeten Protokolle, die für alle Microsoft-Supportfälle erforderlich sind. Debug-Protokolle werden von den Windows-und Mac-Desktop Clients sowie browserbasierten Clients erstellt. Die Protokolle sind Text basiert und werden von unten nach oben gelesen. Sie können mithilfe eines beliebigen textbasierten Editors gelesen und neue Protokolle erstellt werden, wenn Sie sich beim Client anmelden.

Debugprotokolle zeigen die folgenden Datenflüsse:

-   Anmeldung

-   Verbindungsanfragen an Dienste auf mittlerer Ebene 

-   Anruf/Unterhaltung

Die Debugprotokolle werden unter Verwendung der folgenden für das jeweilige Betriebssystem spezifischen Methoden erstellt:

-   Windows:

      Tastenkombination: STRG+ALT+UMSCHALT+1

-   Mac OSX:

      Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1

Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen.

-   Windows: %userprofile%\\Downloads

-   Mac OSX: Downloads

-   Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert

<a name="media-logs"></a>Medienprotokolle
---------------------------

Medienprotokolle enthalten Diagnosedaten zu Audio, Video und Bildschirmfreigabe Sie sind für Supportfälle nur nach Aufforderung erforderlich und können nur von Microsoft geprüft werden. In der folgenden Tabelle wird der Protokollspeicherort aufgeführt.


|Client |Speicherort |
|---------|---------|
|Windows     |%APPDATA%\Microsoft\Teams\media-Stack\\*. Blog         |
|            |%APPDATA%\Microsoft\Teams\skylib\\*. Blog
|            |%APPDATA%\Microsoft\Teams\media-Stack\\*. ETL         |
|Mac OSX     |~/Library/Application-Unterstützung/Microsoft/Teams/Media-Stack/*. Blog         |
|            |~/Library/Application-Unterstützung/Microsoft/Teams/skylib/*. Blog         |



<a name="desktop-logs"></a>Desktopprotokolle
---------------------

Desktopprotokolle, auch bekannt unter Bootstrapper-Protokolle, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser erstellt werden. Wie Medienprotokolle werden diese Protokolle nur auf Anforderung von Microsoft benötigt. Die Protokolle sind textbasiert und können mit jedem Texteditor von oben nach unten gelesen werden.

Windows:

1.  Klicken Sie mit der rechten Maustaste auf **das Microsoft Teams-Symbol im** Infobereich Ihrer Anwendung, und wählen Sie **Protokolle abrufen** aus.

Mac OSX:

1.  Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**

|Client |Speicherort |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application-Unterstützung/Microsoft/Teams/Logs. txt         |
