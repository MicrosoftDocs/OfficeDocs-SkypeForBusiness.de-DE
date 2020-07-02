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
ms.openlocfilehash: 7ad44af297cdfe375f28485e1c4c4e223f616666
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012191"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
=================================================

Es gibt drei Typen von automatisch vom Client erstellten Protokolldateien, die zur Problembehandlung in Microsoft Teams eingesetzt werden können.

-   Debugprotokolle

-   Medienprotokolle

-   Desktopprotokolle

When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.

The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.


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

-   Linux

      Tastenkombination: STRG+ALT+UMSCHALT+1

Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen.

-   Windows: %userprofile%\\Downloads

-   Mac OSX: Downloads

-   Linux: ~/Downloads

-   Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert

<a name="media-logs"></a>Medienprotokolle
---------------------------

Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.


|Client |Speicherort |
|---------|---------|
|Windows     |%APPDATA%\Microsoft\Teams\media-Stack \\ *. Blog         |
|            |%APPDATA%\Microsoft\Teams\skylib \\ *. Blog
|            |%APPDATA%\Microsoft\Teams\media-Stack \\ *. ETL         |
|Mac OSX     |~/Library/Application-Unterstützung/Microsoft/Teams/Media-Stack/*. Blog         |
|            |~/Library/Application-Unterstützung/Microsoft/Teams/skylib/*. Blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/Media-Stack/*. Blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*. Blog         |



<a name="desktop-logs"></a>Desktopprotokolle
---------------------

Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.

Windows:

1.  Klicken Sie mit der rechten Maustaste auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.

Mac OSX:

1.  Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**

Linux

1.  Klicken Sie auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.

|Client |Speicherort |
|---------|---------|
|Windows     |% APPDATA% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application-Unterstützung/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |
