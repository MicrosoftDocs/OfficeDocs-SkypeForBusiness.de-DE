---
title: Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Hier erhalten Sie Informationen zu den von Microsoft Teams erstellten Debug-, Medien- und Desktopprotokollen, zu deren Speicherort und wie diese für die Problembehandlung eingesetzt werden können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a14d6db6c03b540a6495b9028a4f0342ff92636
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716335"
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

    1.  Klicken Sie mit der rechten Maustaste auf **das Microsoft Teams-Symbol im** Infobereich Ihrer Anwendung, und wählen Sie **Protokolle abrufen** aus.

    2.  Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**

    3.  Tastenkombination: STRG+ALT+UMSCHALT+1

-   Mac OSX:

    1.  Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**

    2.  Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1

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

|Client |Speicherort |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
