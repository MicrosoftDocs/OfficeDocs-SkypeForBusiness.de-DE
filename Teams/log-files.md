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
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="5a5df-103">Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a5df-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="5a5df-104">Es gibt drei Typen von automatisch vom Client erstellten Protokolldateien, die zur Problembehandlung in Microsoft Teams eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="5a5df-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="5a5df-105">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="5a5df-105">Debug logs</span></span>

-   <span data-ttu-id="5a5df-106">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="5a5df-106">Media logs</span></span>

-   <span data-ttu-id="5a5df-107">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="5a5df-107">Desktop logs</span></span>

<span data-ttu-id="5a5df-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span><span class="sxs-lookup"><span data-stu-id="5a5df-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="5a5df-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span><span class="sxs-lookup"><span data-stu-id="5a5df-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="5a5df-110">Media or desktop logs are only required if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a5df-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="5a5df-111">The following table outlines the various clients, and their associated logs.</span><span class="sxs-lookup"><span data-stu-id="5a5df-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="5a5df-112">Log files are stored in locations specific to the client and operating system.</span><span class="sxs-lookup"><span data-stu-id="5a5df-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="5a5df-113">Client</span><span class="sxs-lookup"><span data-stu-id="5a5df-113">Client</span></span> |<span data-ttu-id="5a5df-114">Debug</span><span class="sxs-lookup"><span data-stu-id="5a5df-114">Debug</span></span>|<span data-ttu-id="5a5df-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="5a5df-115">Desktop</span></span>|<span data-ttu-id="5a5df-116">Medien</span><span class="sxs-lookup"><span data-stu-id="5a5df-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="5a5df-117">Web</span><span class="sxs-lookup"><span data-stu-id="5a5df-117">Web</span></span>    |<span data-ttu-id="5a5df-118">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-118">X</span></span>         |-         |-         |
|<span data-ttu-id="5a5df-119">Windows</span><span class="sxs-lookup"><span data-stu-id="5a5df-119">Windows</span></span>     |<span data-ttu-id="5a5df-120">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-120">X</span></span>         |<span data-ttu-id="5a5df-121">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-121">X</span></span>         |<span data-ttu-id="5a5df-122">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-122">X</span></span>         |
|<span data-ttu-id="5a5df-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5a5df-123">Mac OSX</span></span>     |<span data-ttu-id="5a5df-124">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-124">X</span></span>         |<span data-ttu-id="5a5df-125">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-125">X</span></span>         |<span data-ttu-id="5a5df-126">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-126">X</span></span>         |
|<span data-ttu-id="5a5df-127">Linux</span><span class="sxs-lookup"><span data-stu-id="5a5df-127">Linux</span></span>     |<span data-ttu-id="5a5df-128">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-128">X</span></span>         |<span data-ttu-id="5a5df-129">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-129">X</span></span>         |<span data-ttu-id="5a5df-130">X</span><span class="sxs-lookup"><span data-stu-id="5a5df-130">X</span></span>         |
|<span data-ttu-id="5a5df-131">iOS</span><span class="sxs-lookup"><span data-stu-id="5a5df-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="5a5df-132">Android</span><span class="sxs-lookup"><span data-stu-id="5a5df-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="5a5df-133">Eine vollständige Liste der unterstützten Betriebssysteme und Browser finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="5a5df-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="5a5df-134">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="5a5df-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="5a5df-135">Dies sind die am häufigsten verwendeten Protokolle, die für alle Microsoft-Supportfälle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5a5df-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="5a5df-136">Debug-Protokolle werden von den Windows-und Mac-Desktop Clients sowie browserbasierten Clients erstellt.</span><span class="sxs-lookup"><span data-stu-id="5a5df-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="5a5df-137">Die Protokolle sind Text basiert und werden von unten nach oben gelesen.</span><span class="sxs-lookup"><span data-stu-id="5a5df-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="5a5df-138">Sie können mithilfe eines beliebigen textbasierten Editors gelesen und neue Protokolle erstellt werden, wenn Sie sich beim Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="5a5df-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="5a5df-139">Debugprotokolle zeigen die folgenden Datenflüsse:</span><span class="sxs-lookup"><span data-stu-id="5a5df-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="5a5df-140">Anmeldung</span><span class="sxs-lookup"><span data-stu-id="5a5df-140">Login</span></span>

-   <span data-ttu-id="5a5df-141">Verbindungsanfragen an Dienste auf mittlerer Ebene </span><span class="sxs-lookup"><span data-stu-id="5a5df-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="5a5df-142">Anruf/Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="5a5df-142">Call/conversation</span></span>

<span data-ttu-id="5a5df-143">Die Debugprotokolle werden unter Verwendung der folgenden für das jeweilige Betriebssystem spezifischen Methoden erstellt:</span><span class="sxs-lookup"><span data-stu-id="5a5df-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="5a5df-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="5a5df-144">Windows:</span></span>

      <span data-ttu-id="5a5df-145">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="5a5df-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="5a5df-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="5a5df-146">Mac OSX:</span></span>

      <span data-ttu-id="5a5df-147">Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="5a5df-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="5a5df-148">Linux</span><span class="sxs-lookup"><span data-stu-id="5a5df-148">Linux:</span></span>

      <span data-ttu-id="5a5df-149">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="5a5df-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="5a5df-150">Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="5a5df-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="5a5df-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="5a5df-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="5a5df-152">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="5a5df-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="5a5df-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="5a5df-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="5a5df-154">Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert</span><span class="sxs-lookup"><span data-stu-id="5a5df-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="5a5df-155">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="5a5df-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="5a5df-156">Media logs contain diagnostic data about audio, video and screen sharing.</span><span class="sxs-lookup"><span data-stu-id="5a5df-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="5a5df-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a5df-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="5a5df-158">The following table outlines the log location.</span><span class="sxs-lookup"><span data-stu-id="5a5df-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="5a5df-159">Client</span><span class="sxs-lookup"><span data-stu-id="5a5df-159">Client</span></span> |<span data-ttu-id="5a5df-160">Speicherort</span><span class="sxs-lookup"><span data-stu-id="5a5df-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5a5df-161">Windows</span><span class="sxs-lookup"><span data-stu-id="5a5df-161">Windows</span></span>     |<span data-ttu-id="5a5df-162">%APPDATA%\Microsoft\Teams\media-Stack \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="5a5df-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="5a5df-163">%APPDATA%\Microsoft\Teams\skylib \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="5a5df-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="5a5df-164">%APPDATA%\Microsoft\Teams\media-Stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="5a5df-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="5a5df-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5a5df-165">Mac OSX</span></span>     |<span data-ttu-id="5a5df-166">~/Library/Application-Unterstützung/Microsoft/Teams/Media-Stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="5a5df-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="5a5df-167">~/Library/Application-Unterstützung/Microsoft/Teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="5a5df-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="5a5df-168">Linux</span><span class="sxs-lookup"><span data-stu-id="5a5df-168">Linux</span></span>       |<span data-ttu-id="5a5df-169">~/.config/Microsoft/Microsoft Teams/Media-Stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="5a5df-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="5a5df-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="5a5df-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="5a5df-171">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="5a5df-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="5a5df-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span><span class="sxs-lookup"><span data-stu-id="5a5df-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="5a5df-173">Like media logs, these logs are only needed if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a5df-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="5a5df-174">The logs are text based and can be read using any text based editor in a top down format.</span><span class="sxs-lookup"><span data-stu-id="5a5df-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="5a5df-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="5a5df-175">Windows:</span></span>

1.  <span data-ttu-id="5a5df-176">Klicken Sie mit der rechten Maustaste auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="5a5df-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="5a5df-177">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="5a5df-177">Mac OsX:</span></span>

1.  <span data-ttu-id="5a5df-178">Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**</span><span class="sxs-lookup"><span data-stu-id="5a5df-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="5a5df-179">Linux</span><span class="sxs-lookup"><span data-stu-id="5a5df-179">Linux:</span></span>

1.  <span data-ttu-id="5a5df-180">Klicken Sie auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="5a5df-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="5a5df-181">Client</span><span class="sxs-lookup"><span data-stu-id="5a5df-181">Client</span></span> |<span data-ttu-id="5a5df-182">Speicherort</span><span class="sxs-lookup"><span data-stu-id="5a5df-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5a5df-183">Windows</span><span class="sxs-lookup"><span data-stu-id="5a5df-183">Windows</span></span>     |<span data-ttu-id="5a5df-184">% APPDATA% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="5a5df-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="5a5df-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5a5df-185">Mac OSX</span></span>     |<span data-ttu-id="5a5df-186">~/Library/Application-Unterstützung/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5a5df-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="5a5df-187">Linux</span><span class="sxs-lookup"><span data-stu-id="5a5df-187">Linux</span></span>       |<span data-ttu-id="5a5df-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5a5df-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |
