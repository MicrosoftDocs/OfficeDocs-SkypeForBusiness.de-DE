---
title: Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Hier erhalten Sie Informationen zu den von Microsoft Teams erstellten Debug-, Medien- und Desktopprotokollen, zu deren Speicherort und wie diese für die Problembehandlung eingesetzt werden können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e0484b84daa1bd8604c5f2caf9cb728f8fce25a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894410"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="07e50-103">Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07e50-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="07e50-104">Es gibt drei Typen von automatisch vom Client erstellten Protokolldateien, die zur Problembehandlung in Microsoft Teams eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="07e50-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="07e50-105">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="07e50-105">Debug logs</span></span>

-   <span data-ttu-id="07e50-106">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="07e50-106">Media logs</span></span>

-   <span data-ttu-id="07e50-107">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="07e50-107">Desktop logs</span></span>

<span data-ttu-id="07e50-p101">Beim Erstellen einer Supportanfrage beim Microsoft-Support fordert Sie der Supportmitarbeiter zur Einreichung von Debugprotokollen auf. Wenn Sie diese Protokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann das Problem von Microsoft schneller behoben werden. Medien- oder Desktopprotokolle werden nur auf Anforderung von Microsoft benötigt.</span><span class="sxs-lookup"><span data-stu-id="07e50-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="07e50-p102">In der folgenden Tabelle werden verschiedene Clients und die jeweils zugehörigen Protokolle aufgeführt. Protokolldateien sind in den für den Client und das Betriebssystem spezifischen Verzeichnissen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="07e50-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="07e50-113">Client</span><span class="sxs-lookup"><span data-stu-id="07e50-113">Client</span></span> |<span data-ttu-id="07e50-114">Debug</span><span class="sxs-lookup"><span data-stu-id="07e50-114">Debug</span></span>|<span data-ttu-id="07e50-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="07e50-115">Desktop</span></span>|<span data-ttu-id="07e50-116">Medien</span><span class="sxs-lookup"><span data-stu-id="07e50-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="07e50-117">Web</span><span class="sxs-lookup"><span data-stu-id="07e50-117">Web</span></span>    |<span data-ttu-id="07e50-118">X</span><span class="sxs-lookup"><span data-stu-id="07e50-118">X</span></span>         |-         |-         |
|<span data-ttu-id="07e50-119">Windows</span><span class="sxs-lookup"><span data-stu-id="07e50-119">Windows</span></span>     |<span data-ttu-id="07e50-120">X</span><span class="sxs-lookup"><span data-stu-id="07e50-120">X</span></span>         |<span data-ttu-id="07e50-121">X</span><span class="sxs-lookup"><span data-stu-id="07e50-121">X</span></span>         |<span data-ttu-id="07e50-122">X</span><span class="sxs-lookup"><span data-stu-id="07e50-122">X</span></span>         |
|<span data-ttu-id="07e50-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="07e50-123">Mac OSX</span></span>     |<span data-ttu-id="07e50-124">X</span><span class="sxs-lookup"><span data-stu-id="07e50-124">X</span></span>         |<span data-ttu-id="07e50-125">X</span><span class="sxs-lookup"><span data-stu-id="07e50-125">X</span></span>         |<span data-ttu-id="07e50-126">X</span><span class="sxs-lookup"><span data-stu-id="07e50-126">X</span></span>         |
|<span data-ttu-id="07e50-127">iOS</span><span class="sxs-lookup"><span data-stu-id="07e50-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="07e50-128">Android</span><span class="sxs-lookup"><span data-stu-id="07e50-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="07e50-129">Eine vollständige Liste der unterstützten Betriebssysteme und Browser finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="07e50-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="07e50-130">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="07e50-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="07e50-131">Dies sind die am häufigsten verwendeten Protokolle und für alle Microsoft Support-Anfragen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="07e50-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="07e50-132">Debug-Protokolle werden von der Windows- und Mac-Desktopclients als auch browserbasierte Clients erzeugt.</span><span class="sxs-lookup"><span data-stu-id="07e50-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="07e50-133">Die Protokolle sind Text basieren und werden von unten nach oben lesen.</span><span class="sxs-lookup"><span data-stu-id="07e50-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="07e50-134">Mit einem beliebigen-basierten Texteditor gelesen werden können und neue Protokolle werden erstellt, wenn sich der Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="07e50-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="07e50-135">Debugprotokolle zeigen die folgenden Datenflüsse:</span><span class="sxs-lookup"><span data-stu-id="07e50-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="07e50-136">Anmeldung</span><span class="sxs-lookup"><span data-stu-id="07e50-136">Login</span></span>

-   <span data-ttu-id="07e50-137">Verbindungsanfragen an Dienste auf mittlerer Ebene </span><span class="sxs-lookup"><span data-stu-id="07e50-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="07e50-138">Anruf/Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="07e50-138">Call/conversation</span></span>

<span data-ttu-id="07e50-139">Die Debugprotokolle werden unter Verwendung der folgenden für das jeweilige Betriebssystem spezifischen Methoden erstellt:</span><span class="sxs-lookup"><span data-stu-id="07e50-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="07e50-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="07e50-140">Windows:</span></span>

      <span data-ttu-id="07e50-141">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="07e50-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="07e50-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="07e50-142">Mac OSX:</span></span>

      <span data-ttu-id="07e50-143">Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="07e50-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="07e50-144">Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="07e50-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="07e50-145">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="07e50-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="07e50-146">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="07e50-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="07e50-147">Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert</span><span class="sxs-lookup"><span data-stu-id="07e50-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="07e50-148">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="07e50-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="07e50-p104">Medienprotokolle enthalten Diagnosedaten zu Audio, Video und Bildschirmfreigabe Sie sind für Supportfälle nur nach Aufforderung erforderlich und können nur von Microsoft geprüft werden. In der folgenden Tabelle wird der Protokollspeicherort aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="07e50-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="07e50-152">Client</span><span class="sxs-lookup"><span data-stu-id="07e50-152">Client</span></span> |<span data-ttu-id="07e50-153">Speicherort</span><span class="sxs-lookup"><span data-stu-id="07e50-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="07e50-154">Windows</span><span class="sxs-lookup"><span data-stu-id="07e50-154">Windows</span></span>     |<span data-ttu-id="07e50-155">%appdata%\Microsoft\Teams\media-Stack\*ETL</span><span class="sxs-lookup"><span data-stu-id="07e50-155">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="07e50-156">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="07e50-156">Mac OSX</span></span>     |<span data-ttu-id="07e50-157">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="07e50-157">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="07e50-158">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="07e50-158">Desktop logs</span></span>
---------------------

<span data-ttu-id="07e50-p105">Desktopprotokolle, auch bekannt unter Bootstrapper-Protokolle, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser erstellt werden. Wie Medienprotokolle werden diese Protokolle nur auf Anforderung von Microsoft benötigt. Die Protokolle sind textbasiert und können mit jedem Texteditor von oben nach unten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="07e50-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="07e50-162">Windows:</span><span class="sxs-lookup"><span data-stu-id="07e50-162">Windows:</span></span>

1.  <span data-ttu-id="07e50-163">Klicken Sie mit der rechten Maustaste auf **das Microsoft Teams-Symbol im** Infobereich Ihrer Anwendung, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="07e50-163">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="07e50-164">Mac OSX ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="07e50-164">Mac OsX:</span></span>

1.  <span data-ttu-id="07e50-165">Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**</span><span class="sxs-lookup"><span data-stu-id="07e50-165">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="07e50-166">Client</span><span class="sxs-lookup"><span data-stu-id="07e50-166">Client</span></span> |<span data-ttu-id="07e50-167">Speicherort</span><span class="sxs-lookup"><span data-stu-id="07e50-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="07e50-168">Windows</span><span class="sxs-lookup"><span data-stu-id="07e50-168">Windows</span></span>     |<span data-ttu-id="07e50-169">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="07e50-169">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="07e50-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="07e50-170">Mac OSX</span></span>     |<span data-ttu-id="07e50-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="07e50-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
