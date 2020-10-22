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
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650828"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="3fefb-103">Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fefb-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="3fefb-104">Es gibt drei Typen von automatisch vom Client erstellten Protokolldateien, die zur Problembehandlung in Microsoft Teams eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="3fefb-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="3fefb-105">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="3fefb-105">Debug logs</span></span>

-   <span data-ttu-id="3fefb-106">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="3fefb-106">Media logs</span></span>

-   <span data-ttu-id="3fefb-107">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="3fefb-107">Desktop logs</span></span>

<span data-ttu-id="3fefb-p101">Beim Erstellen einer Supportanfrage beim Microsoft-Support fordert Sie der Supportmitarbeiter zur Einreichung von Debugprotokollen auf. Wenn Sie diese Protokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann das Problem von Microsoft schneller behoben werden. Medien- oder Desktopprotokolle werden nur auf Anforderung von Microsoft benötigt.</span><span class="sxs-lookup"><span data-stu-id="3fefb-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="3fefb-p102">In der folgenden Tabelle werden verschiedene Clients und die jeweils zugehörigen Protokolle aufgeführt. Protokolldateien sind in den für den Client und das Betriebssystem spezifischen Verzeichnissen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3fefb-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="3fefb-113">Client</span><span class="sxs-lookup"><span data-stu-id="3fefb-113">Client</span></span> |<span data-ttu-id="3fefb-114">Debug</span><span class="sxs-lookup"><span data-stu-id="3fefb-114">Debug</span></span>|<span data-ttu-id="3fefb-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="3fefb-115">Desktop</span></span>|<span data-ttu-id="3fefb-116">Medien</span><span class="sxs-lookup"><span data-stu-id="3fefb-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="3fefb-117">Web</span><span class="sxs-lookup"><span data-stu-id="3fefb-117">Web</span></span>    |<span data-ttu-id="3fefb-118">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-118">X</span></span>         |-         |-         |
|<span data-ttu-id="3fefb-119">Windows</span><span class="sxs-lookup"><span data-stu-id="3fefb-119">Windows</span></span>     |<span data-ttu-id="3fefb-120">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-120">X</span></span>         |<span data-ttu-id="3fefb-121">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-121">X</span></span>         |<span data-ttu-id="3fefb-122">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-122">X</span></span>         |
|<span data-ttu-id="3fefb-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3fefb-123">Mac OSX</span></span>     |<span data-ttu-id="3fefb-124">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-124">X</span></span>         |<span data-ttu-id="3fefb-125">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-125">X</span></span>         |<span data-ttu-id="3fefb-126">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-126">X</span></span>         |
|<span data-ttu-id="3fefb-127">Linux</span><span class="sxs-lookup"><span data-stu-id="3fefb-127">Linux</span></span>     |<span data-ttu-id="3fefb-128">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-128">X</span></span>         |<span data-ttu-id="3fefb-129">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-129">X</span></span>         |<span data-ttu-id="3fefb-130">X</span><span class="sxs-lookup"><span data-stu-id="3fefb-130">X</span></span>         |
|<span data-ttu-id="3fefb-131">iOS</span><span class="sxs-lookup"><span data-stu-id="3fefb-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="3fefb-132">Android</span><span class="sxs-lookup"><span data-stu-id="3fefb-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="3fefb-133">Eine vollständige Liste der unterstützten Betriebssysteme und Browser finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="3fefb-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="3fefb-134">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="3fefb-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="3fefb-135">Dies sind die am häufigsten verwendeten Protokolle, die für alle Microsoft-Supportfälle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3fefb-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="3fefb-136">Debug-Protokolle werden von den Windows-und Mac-Desktop Clients sowie browserbasierten Clients erstellt.</span><span class="sxs-lookup"><span data-stu-id="3fefb-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="3fefb-137">Die Protokolle sind Text basiert und werden von unten nach oben gelesen.</span><span class="sxs-lookup"><span data-stu-id="3fefb-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="3fefb-138">Sie können mithilfe eines beliebigen textbasierten Editors gelesen und neue Protokolle erstellt werden, wenn Sie sich beim Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="3fefb-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="3fefb-139">Debugprotokolle zeigen die folgenden Datenflüsse:</span><span class="sxs-lookup"><span data-stu-id="3fefb-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="3fefb-140">Anmeldung</span><span class="sxs-lookup"><span data-stu-id="3fefb-140">Login</span></span>

-   <span data-ttu-id="3fefb-141">Verbindungsanfragen an Dienste auf mittlerer Ebene </span><span class="sxs-lookup"><span data-stu-id="3fefb-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="3fefb-142">Anruf/Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="3fefb-142">Call/conversation</span></span>

<span data-ttu-id="3fefb-143">Die Debugprotokolle werden unter Verwendung der folgenden für das jeweilige Betriebssystem spezifischen Methoden erstellt:</span><span class="sxs-lookup"><span data-stu-id="3fefb-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="3fefb-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="3fefb-144">Windows:</span></span>

      <span data-ttu-id="3fefb-145">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="3fefb-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="3fefb-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="3fefb-146">Mac OSX:</span></span>

      <span data-ttu-id="3fefb-147">Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="3fefb-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="3fefb-148">Linux</span><span class="sxs-lookup"><span data-stu-id="3fefb-148">Linux:</span></span>

      <span data-ttu-id="3fefb-149">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="3fefb-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="3fefb-150">Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="3fefb-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="3fefb-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="3fefb-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="3fefb-152">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="3fefb-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="3fefb-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="3fefb-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="3fefb-154">Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert</span><span class="sxs-lookup"><span data-stu-id="3fefb-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="3fefb-155">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="3fefb-155">Media logs</span></span>
---------------------------

<span data-ttu-id="3fefb-156">Medienprotokolle enthalten diagnostische Daten zur Audio-, Video-und Bildschirmfreigabe in Teams-Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="3fefb-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="3fefb-157">Sie sind für Supportfälle erforderlich, die mit anrufbezogenen Problemen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="3fefb-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="3fefb-158">Die Medien Protokollierung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3fefb-158">Media logging is turned off by default.</span></span> <span data-ttu-id="3fefb-159">Zum Protokollieren von Diagnosedaten für Teams-Besprechungen müssen die Benutzer die Option im Teams-Client aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3fefb-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="3fefb-160">Wechseln Sie zu **Einstellungen**  >  **Allgemein**, aktivieren Sie das Kontrollkästchen **Protokollierung für die Besprechungs Diagnose aktivieren (erfordert einen Neustart von Teams**), und starten Sie dann Teams neu, und reproduzieren Sie das Problem.</span><span class="sxs-lookup"><span data-stu-id="3fefb-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="3fefb-161">In der folgenden Tabelle werden die Speicherorte des Medien Protokolls erläutert.</span><span class="sxs-lookup"><span data-stu-id="3fefb-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="3fefb-162">Wenn Sie die Protokolldateien an den Microsoft-Support senden, überprüfen Sie bitte den Zeitstempel der Protokolldateien, um sicherzustellen, dass die Protokolle den Zeitrahmen abdecken, wenn Sie das Problem reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="3fefb-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="3fefb-163">Client</span><span class="sxs-lookup"><span data-stu-id="3fefb-163">Client</span></span> |<span data-ttu-id="3fefb-164">Speicherort</span><span class="sxs-lookup"><span data-stu-id="3fefb-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="3fefb-165">Windows</span><span class="sxs-lookup"><span data-stu-id="3fefb-165">Windows</span></span>     |<span data-ttu-id="3fefb-166">%APPDATA%\Microsoft\Teams\media-Stack \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="3fefb-167">%APPDATA%\Microsoft\Teams\skylib \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="3fefb-168">%APPDATA%\Microsoft\Teams\media-Stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="3fefb-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="3fefb-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3fefb-169">Mac OSX</span></span>     |<span data-ttu-id="3fefb-170">~/Library/Application-Unterstützung/Microsoft/Teams/Media-Stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="3fefb-171">~/Library/Application-Unterstützung/Microsoft/Teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="3fefb-172">Linux</span><span class="sxs-lookup"><span data-stu-id="3fefb-172">Linux</span></span>       |<span data-ttu-id="3fefb-173">~/.config/Microsoft/Microsoft Teams/Media-Stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="3fefb-174">~/.config/Microsoft/Microsoft Teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="3fefb-175">Nachfolgend finden Sie eine Liste der generierten Protokolldateien und der darin enthaltenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="3fefb-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="3fefb-176">Name der Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="3fefb-176">Log file name</span></span>  |<span data-ttu-id="3fefb-177">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fefb-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="3fefb-178">Teams. msrtc-0-s1039525249. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="3fefb-179">Enthält Informationen im Zusammenhang mit dem Medien Stapel.</span><span class="sxs-lookup"><span data-stu-id="3fefb-179">Contains information related to the media stack.</span></span> <span data-ttu-id="3fefb-180">Dazu gehören Kanalstatus wie Auflösung, verwendete Decoder und Encoder sowie die Anzahl der gesendeten und empfangenen Frames sowie der Kamera-und videobasierte schlechte VBSS-Sitzungsstatus (Screen Sharing).</span><span class="sxs-lookup"><span data-stu-id="3fefb-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="3fefb-181">rtmcontrol. msrtc-0-2415069487. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="3fefb-182">Zeichnet Informationen zu Remote Steuerungsaktionen auf, beispielsweise den Zeitstempel, wenn das Steuerelement angegeben wird, und Mauszeiger Informationen.</span><span class="sxs-lookup"><span data-stu-id="3fefb-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="3fefb-183">Teams_MediaStackETW -2-u-XR-u. ETL</span><span class="sxs-lookup"><span data-stu-id="3fefb-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="3fefb-184">Zeichnet Medien Stapel-Ablaufverfolgungsereignisse auf.</span><span class="sxs-lookup"><span data-stu-id="3fefb-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="3fefb-185">Debug-0-s2790420889. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="3fefb-186">Enthält Informationen zum Medien Agenten, einschließlich der Rendering-Qualität.</span><span class="sxs-lookup"><span data-stu-id="3fefb-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="3fefb-187">tscalling-0-2061129496. Blog</span><span class="sxs-lookup"><span data-stu-id="3fefb-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="3fefb-188">Zeichnet Ereignisse in der TS-Aufruf-API auf.</span><span class="sxs-lookup"><span data-stu-id="3fefb-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="3fefb-189">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="3fefb-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="3fefb-p108">Desktopprotokolle, auch bekannt unter Bootstrapper-Protokolle, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser erstellt werden. Wie Medienprotokolle werden diese Protokolle nur auf Anforderung von Microsoft benötigt. Die Protokolle sind textbasiert und können mit jedem Texteditor von oben nach unten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="3fefb-p108">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="3fefb-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="3fefb-193">Windows:</span></span>

1.  <span data-ttu-id="3fefb-194">Klicken Sie mit der rechten Maustaste auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="3fefb-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="3fefb-195">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="3fefb-195">Mac OsX:</span></span>

1.  <span data-ttu-id="3fefb-196">Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**</span><span class="sxs-lookup"><span data-stu-id="3fefb-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="3fefb-197">Linux</span><span class="sxs-lookup"><span data-stu-id="3fefb-197">Linux:</span></span>

1.  <span data-ttu-id="3fefb-198">Klicken Sie auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="3fefb-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="3fefb-199">Client</span><span class="sxs-lookup"><span data-stu-id="3fefb-199">Client</span></span> |<span data-ttu-id="3fefb-200">Speicherort</span><span class="sxs-lookup"><span data-stu-id="3fefb-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="3fefb-201">Windows</span><span class="sxs-lookup"><span data-stu-id="3fefb-201">Windows</span></span>     |<span data-ttu-id="3fefb-202">% APPDATA% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="3fefb-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="3fefb-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3fefb-203">Mac OSX</span></span>     |<span data-ttu-id="3fefb-204">~/Library/Application-Unterstützung/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="3fefb-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="3fefb-205">Linux</span><span class="sxs-lookup"><span data-stu-id="3fefb-205">Linux</span></span>       |<span data-ttu-id="3fefb-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="3fefb-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="3fefb-207">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3fefb-207">Related topics</span></span>

[<span data-ttu-id="3fefb-208">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="3fefb-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
