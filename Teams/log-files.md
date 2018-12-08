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
ms.openlocfilehash: bf42d76e1e17dc81b1c3d0ab603050c6e2d25d71
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2018
ms.locfileid: "27201333"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="82f10-103">Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82f10-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="82f10-104">Es gibt drei Typen von automatisch vom Client erstellten Protokolldateien, die zur Problembehandlung in Microsoft Teams eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="82f10-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="82f10-105">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="82f10-105">Debug logs</span></span>

-   <span data-ttu-id="82f10-106">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="82f10-106">Media logs</span></span>

-   <span data-ttu-id="82f10-107">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="82f10-107">Desktop logs</span></span>

<span data-ttu-id="82f10-p101">Beim Erstellen einer Supportanfrage beim Microsoft-Support fordert Sie der Supportmitarbeiter zur Einreichung von Debugprotokollen auf. Wenn Sie diese Protokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann das Problem von Microsoft schneller behoben werden. Medien- oder Desktopprotokolle werden nur auf Anforderung von Microsoft benötigt.</span><span class="sxs-lookup"><span data-stu-id="82f10-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="82f10-p102">In der folgenden Tabelle werden verschiedene Clients und die jeweils zugehörigen Protokolle aufgeführt. Protokolldateien sind in den für den Client und das Betriebssystem spezifischen Verzeichnissen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="82f10-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="82f10-113">Client</span><span class="sxs-lookup"><span data-stu-id="82f10-113">Client</span></span> |<span data-ttu-id="82f10-114">Debug</span><span class="sxs-lookup"><span data-stu-id="82f10-114">Debug</span></span>|<span data-ttu-id="82f10-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="82f10-115">Desktop</span></span>|<span data-ttu-id="82f10-116">Medien</span><span class="sxs-lookup"><span data-stu-id="82f10-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="82f10-117">Web</span><span class="sxs-lookup"><span data-stu-id="82f10-117">Web</span></span>    |<span data-ttu-id="82f10-118">X</span><span class="sxs-lookup"><span data-stu-id="82f10-118">X</span></span>         |-         |-         |
|<span data-ttu-id="82f10-119">Windows</span><span class="sxs-lookup"><span data-stu-id="82f10-119">Windows</span></span>     |<span data-ttu-id="82f10-120">X</span><span class="sxs-lookup"><span data-stu-id="82f10-120">X</span></span>         |<span data-ttu-id="82f10-121">X</span><span class="sxs-lookup"><span data-stu-id="82f10-121">X</span></span>         |<span data-ttu-id="82f10-122">X</span><span class="sxs-lookup"><span data-stu-id="82f10-122">X</span></span>         |
|<span data-ttu-id="82f10-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="82f10-123">Mac OSX</span></span>     |<span data-ttu-id="82f10-124">X</span><span class="sxs-lookup"><span data-stu-id="82f10-124">X</span></span>         |<span data-ttu-id="82f10-125">X</span><span class="sxs-lookup"><span data-stu-id="82f10-125">X</span></span>         |<span data-ttu-id="82f10-126">X</span><span class="sxs-lookup"><span data-stu-id="82f10-126">X</span></span>         |
|<span data-ttu-id="82f10-127">iOS</span><span class="sxs-lookup"><span data-stu-id="82f10-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="82f10-128">Android</span><span class="sxs-lookup"><span data-stu-id="82f10-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="82f10-129">Eine vollständige Liste der unterstützten Betriebssysteme und Browser finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="82f10-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="82f10-130">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="82f10-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="82f10-131">Dies sind die am häufigsten verwendeten Protokolle und für alle Microsoft Support-Anfragen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="82f10-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="82f10-132">Debug-Protokolle werden von der Windows- und Mac-Desktopclients als auch browserbasierte Clients erzeugt.</span><span class="sxs-lookup"><span data-stu-id="82f10-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="82f10-133">Die Protokolle sind Text basieren und werden von unten nach oben lesen.</span><span class="sxs-lookup"><span data-stu-id="82f10-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="82f10-134">Mit einem beliebigen-basierten Texteditor gelesen werden können und neue Protokolle werden erstellt, wenn sich der Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="82f10-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="82f10-135">Debugprotokolle zeigen die folgenden Datenflüsse:</span><span class="sxs-lookup"><span data-stu-id="82f10-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="82f10-136">Anmeldung</span><span class="sxs-lookup"><span data-stu-id="82f10-136">Login</span></span>

-   <span data-ttu-id="82f10-137">Verbindungsanfragen an Dienste auf mittlerer Ebene </span><span class="sxs-lookup"><span data-stu-id="82f10-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="82f10-138">Anruf/Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="82f10-138">Call/conversation</span></span>

<span data-ttu-id="82f10-139">Die Debugprotokolle werden unter Verwendung der folgenden für das jeweilige Betriebssystem spezifischen Methoden erstellt:</span><span class="sxs-lookup"><span data-stu-id="82f10-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="82f10-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="82f10-140">Windows:</span></span>

      <span data-ttu-id="82f10-141">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="82f10-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="82f10-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="82f10-142">Mac OSX:</span></span>

      <span data-ttu-id="82f10-143">Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="82f10-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="82f10-144">Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="82f10-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="82f10-145">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="82f10-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="82f10-146">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="82f10-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="82f10-147">Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert</span><span class="sxs-lookup"><span data-stu-id="82f10-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="82f10-148">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="82f10-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="82f10-p104">Medienprotokolle enthalten Diagnosedaten zu Audio, Video und Bildschirmfreigabe Sie sind für Supportfälle nur nach Aufforderung erforderlich und können nur von Microsoft geprüft werden. In der folgenden Tabelle wird der Protokollspeicherort aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="82f10-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="82f10-152">Client</span><span class="sxs-lookup"><span data-stu-id="82f10-152">Client</span></span> |<span data-ttu-id="82f10-153">Speicherort</span><span class="sxs-lookup"><span data-stu-id="82f10-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="82f10-154">Windows</span><span class="sxs-lookup"><span data-stu-id="82f10-154">Windows</span></span>     |<span data-ttu-id="82f10-155">%appdata%\Microsoft\Teams\media-Stack\*ETL</span><span class="sxs-lookup"><span data-stu-id="82f10-155">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="82f10-156">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="82f10-156">Mac OSX</span></span>     |<span data-ttu-id="82f10-157">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="82f10-157">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="82f10-158">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="82f10-158">Desktop logs</span></span>
---------------------

<span data-ttu-id="82f10-p105">Desktopprotokolle, auch bekannt unter Bootstrapper-Protokolle, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser erstellt werden. Wie Medienprotokolle werden diese Protokolle nur auf Anforderung von Microsoft benötigt. Die Protokolle sind textbasiert und können mit jedem Texteditor von oben nach unten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="82f10-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="82f10-162">Windows:</span><span class="sxs-lookup"><span data-stu-id="82f10-162">Windows:</span></span>

  1.  <span data-ttu-id="82f10-163">Klicken Sie mit der rechten Maustaste auf **das Microsoft Teams-Symbol im** Infobereich Ihrer Anwendung, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="82f10-163">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

  2.  <span data-ttu-id="82f10-164">Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**</span><span class="sxs-lookup"><span data-stu-id="82f10-164">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="82f10-165">Mac OSX ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="82f10-165">Mac OsX:</span></span>

1.  <span data-ttu-id="82f10-166">Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**</span><span class="sxs-lookup"><span data-stu-id="82f10-166">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="82f10-167">Client</span><span class="sxs-lookup"><span data-stu-id="82f10-167">Client</span></span> |<span data-ttu-id="82f10-168">Speicherort</span><span class="sxs-lookup"><span data-stu-id="82f10-168">Location</span></span> |
|---------|---------|
|<span data-ttu-id="82f10-169">Windows</span><span class="sxs-lookup"><span data-stu-id="82f10-169">Windows</span></span>     |<span data-ttu-id="82f10-170">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="82f10-170">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="82f10-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="82f10-171">Mac OSX</span></span>     |<span data-ttu-id="82f10-172">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="82f10-172">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
