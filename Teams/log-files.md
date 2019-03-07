---
title: Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Hier erhalten Sie Informationen zu den von Microsoft Teams erstellten Debug-, Medien- und Desktopprotokollen, zu deren Speicherort und wie diese für die Problembehandlung eingesetzt werden können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4809b1be78d6c7732038aa459943b3ed770a4c30
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458852"
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

Dies sind die am häufigsten verwendeten Protokolle und für alle Microsoft Support-Anfragen sind erforderlich. Debug-Protokolle werden von der Windows- und Mac-Desktopclients als auch browserbasierte Clients erzeugt. Die Protokolle sind Text basieren und werden von unten nach oben lesen. Mit einem beliebigen-basierten Texteditor gelesen werden können und neue Protokolle werden erstellt, wenn sich der Client anmelden.

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
|Windows     |%appdata%\Microsoft\Teams\media-Stack\*ETL         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack\*.blog         |


<a name="desktop-logs"></a>Desktopprotokolle
---------------------

Desktopprotokolle, auch bekannt unter Bootstrapper-Protokolle, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser erstellt werden. Wie Medienprotokolle werden diese Protokolle nur auf Anforderung von Microsoft benötigt. Die Protokolle sind textbasiert und können mit jedem Texteditor von oben nach unten gelesen werden.

Windows:

  1.  Klicken Sie mit der rechten Maustaste auf **das Microsoft Teams-Symbol im** Infobereich Ihrer Anwendung, und wählen Sie **Protokolle abrufen** aus.

  2.  Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**

Mac OSX ausgeführt werden:

1.  Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**

|Client |Speicherort |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
