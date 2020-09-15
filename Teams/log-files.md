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
ms.openlocfilehash: 468f0f67743f7cd0e11ff28e4484f70a71af3b64
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766759"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="73247-103">Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73247-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="73247-104">Es gibt drei Typen von automatisch vom Client erstellten Protokolldateien, die zur Problembehandlung in Microsoft Teams eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="73247-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="73247-105">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="73247-105">Debug logs</span></span>

-   <span data-ttu-id="73247-106">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="73247-106">Media logs</span></span>

-   <span data-ttu-id="73247-107">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="73247-107">Desktop logs</span></span>

<span data-ttu-id="73247-p101">Beim Erstellen einer Supportanfrage beim Microsoft-Support fordert Sie der Supportmitarbeiter zur Einreichung von Debugprotokollen auf. Wenn Sie diese Protokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann das Problem von Microsoft schneller behoben werden. Medien- oder Desktopprotokolle werden nur auf Anforderung von Microsoft benötigt.</span><span class="sxs-lookup"><span data-stu-id="73247-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="73247-p102">In der folgenden Tabelle werden verschiedene Clients und die jeweils zugehörigen Protokolle aufgeführt. Protokolldateien sind in den für den Client und das Betriebssystem spezifischen Verzeichnissen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="73247-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="73247-113">Client</span><span class="sxs-lookup"><span data-stu-id="73247-113">Client</span></span> |<span data-ttu-id="73247-114">Debug</span><span class="sxs-lookup"><span data-stu-id="73247-114">Debug</span></span>|<span data-ttu-id="73247-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="73247-115">Desktop</span></span>|<span data-ttu-id="73247-116">Medien</span><span class="sxs-lookup"><span data-stu-id="73247-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="73247-117">Web</span><span class="sxs-lookup"><span data-stu-id="73247-117">Web</span></span>    |<span data-ttu-id="73247-118">X</span><span class="sxs-lookup"><span data-stu-id="73247-118">X</span></span>         |-         |-         |
|<span data-ttu-id="73247-119">Windows</span><span class="sxs-lookup"><span data-stu-id="73247-119">Windows</span></span>     |<span data-ttu-id="73247-120">X</span><span class="sxs-lookup"><span data-stu-id="73247-120">X</span></span>         |<span data-ttu-id="73247-121">X</span><span class="sxs-lookup"><span data-stu-id="73247-121">X</span></span>         |<span data-ttu-id="73247-122">X</span><span class="sxs-lookup"><span data-stu-id="73247-122">X</span></span>         |
|<span data-ttu-id="73247-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="73247-123">Mac OSX</span></span>     |<span data-ttu-id="73247-124">X</span><span class="sxs-lookup"><span data-stu-id="73247-124">X</span></span>         |<span data-ttu-id="73247-125">X</span><span class="sxs-lookup"><span data-stu-id="73247-125">X</span></span>         |<span data-ttu-id="73247-126">X</span><span class="sxs-lookup"><span data-stu-id="73247-126">X</span></span>         |
|<span data-ttu-id="73247-127">Linux</span><span class="sxs-lookup"><span data-stu-id="73247-127">Linux</span></span>     |<span data-ttu-id="73247-128">X</span><span class="sxs-lookup"><span data-stu-id="73247-128">X</span></span>         |<span data-ttu-id="73247-129">X</span><span class="sxs-lookup"><span data-stu-id="73247-129">X</span></span>         |<span data-ttu-id="73247-130">X</span><span class="sxs-lookup"><span data-stu-id="73247-130">X</span></span>         |
|<span data-ttu-id="73247-131">iOS</span><span class="sxs-lookup"><span data-stu-id="73247-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="73247-132">Android</span><span class="sxs-lookup"><span data-stu-id="73247-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="73247-133">Eine vollständige Liste der unterstützten Betriebssysteme und Browser finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="73247-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="73247-134">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="73247-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="73247-135">Dies sind die am häufigsten verwendeten Protokolle, die für alle Microsoft-Supportfälle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="73247-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="73247-136">Debug-Protokolle werden von den Windows-und Mac-Desktop Clients sowie browserbasierten Clients erstellt.</span><span class="sxs-lookup"><span data-stu-id="73247-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="73247-137">Die Protokolle sind Text basiert und werden von unten nach oben gelesen.</span><span class="sxs-lookup"><span data-stu-id="73247-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="73247-138">Sie können mithilfe eines beliebigen textbasierten Editors gelesen und neue Protokolle erstellt werden, wenn Sie sich beim Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="73247-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="73247-139">Debugprotokolle zeigen die folgenden Datenflüsse:</span><span class="sxs-lookup"><span data-stu-id="73247-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="73247-140">Anmeldung</span><span class="sxs-lookup"><span data-stu-id="73247-140">Login</span></span>

-   <span data-ttu-id="73247-141">Verbindungsanfragen an Dienste auf mittlerer Ebene </span><span class="sxs-lookup"><span data-stu-id="73247-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="73247-142">Anruf/Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="73247-142">Call/conversation</span></span>

<span data-ttu-id="73247-143">Die Debugprotokolle werden unter Verwendung der folgenden für das jeweilige Betriebssystem spezifischen Methoden erstellt:</span><span class="sxs-lookup"><span data-stu-id="73247-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="73247-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="73247-144">Windows:</span></span>

      <span data-ttu-id="73247-145">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="73247-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="73247-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="73247-146">Mac OSX:</span></span>

      <span data-ttu-id="73247-147">Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="73247-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="73247-148">Linux</span><span class="sxs-lookup"><span data-stu-id="73247-148">Linux:</span></span>

      <span data-ttu-id="73247-149">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="73247-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="73247-150">Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="73247-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="73247-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="73247-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="73247-152">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="73247-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="73247-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="73247-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="73247-154">Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert</span><span class="sxs-lookup"><span data-stu-id="73247-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="73247-155">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="73247-155">Media logs</span></span>
---------------------------

<span data-ttu-id="73247-156">Medienprotokolle enthalten diagnostische Daten zur Audio-, Video-und Bildschirmfreigabe in Teams-Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="73247-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="73247-157">Sie werden für Supportfälle nur auf Anfrage benötigt und können nur von Microsoft überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="73247-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> 

<span data-ttu-id="73247-158">Die Medien Protokollierung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="73247-158">Media logging is turned off by default.</span></span> <span data-ttu-id="73247-159">Zum Protokollieren von Diagnosedaten für Teams-Besprechungen müssen die Benutzer die Option im Teams-Client aktivieren.</span><span class="sxs-lookup"><span data-stu-id="73247-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="73247-160">Wechseln Sie zu **Einstellungen**  >  **Allgemein**, aktivieren Sie das Kontrollkästchen **Protokollierung für die Besprechungs Diagnose aktivieren (erfordert einen Neustart von Teams**), und starten Sie dann Teams neu.</span><span class="sxs-lookup"><span data-stu-id="73247-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams.</span></span>

<span data-ttu-id="73247-161">In der folgenden Tabelle werden die Protokollspeicherorte erläutert.</span><span class="sxs-lookup"><span data-stu-id="73247-161">The following table outlines the log locations.</span></span>

|<span data-ttu-id="73247-162">Client</span><span class="sxs-lookup"><span data-stu-id="73247-162">Client</span></span> |<span data-ttu-id="73247-163">Speicherort</span><span class="sxs-lookup"><span data-stu-id="73247-163">Location</span></span> |
|---------|---------|
|<span data-ttu-id="73247-164">Windows</span><span class="sxs-lookup"><span data-stu-id="73247-164">Windows</span></span>     |<span data-ttu-id="73247-165">%APPDATA%\Microsoft\Teams\media-Stack \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-165">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="73247-166">%APPDATA%\Microsoft\Teams\skylib \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-166">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="73247-167">%APPDATA%\Microsoft\Teams\media-Stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="73247-167">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="73247-168">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="73247-168">Mac OSX</span></span>     |<span data-ttu-id="73247-169">~/Library/Application-Unterstützung/Microsoft/Teams/Media-Stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-169">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="73247-170">~/Library/Application-Unterstützung/Microsoft/Teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-170">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="73247-171">Linux</span><span class="sxs-lookup"><span data-stu-id="73247-171">Linux</span></span>       |<span data-ttu-id="73247-172">~/.config/Microsoft/Microsoft Teams/Media-Stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-172">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="73247-173">~/.config/Microsoft/Microsoft Teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-173">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="73247-174">Nachfolgend finden Sie eine Liste der generierten Protokolldateien und der darin enthaltenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="73247-174">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="73247-175">Name der Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="73247-175">Log file name</span></span>  |<span data-ttu-id="73247-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73247-176">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="73247-177">Teams. msrtc-0-s1039525249. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-177">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="73247-178">Enthält Informationen im Zusammenhang mit dem Medien Stapel.</span><span class="sxs-lookup"><span data-stu-id="73247-178">Contains information related to the media stack.</span></span> <span data-ttu-id="73247-179">Dazu gehören Kanalstatus wie Auflösung, verwendete Decoder und Encoder sowie die Anzahl der gesendeten und empfangenen Frames sowie der Kamera-und videobasierte schlechte VBSS-Sitzungsstatus (Screen Sharing).</span><span class="sxs-lookup"><span data-stu-id="73247-179">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="73247-180">rtmcontrol. msrtc-0-2415069487. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-180">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="73247-181">Zeichnet Informationen zu Remote Steuerungsaktionen auf, beispielsweise den Zeitstempel, wenn das Steuerelement angegeben wird, und Mauszeiger Informationen.</span><span class="sxs-lookup"><span data-stu-id="73247-181">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="73247-182">Teams_MediaStackETW -2-u-XR-u. ETL</span><span class="sxs-lookup"><span data-stu-id="73247-182">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="73247-183">Zeichnet Medien Stapel-Ablaufverfolgungsereignisse auf.</span><span class="sxs-lookup"><span data-stu-id="73247-183">Records media stack trace events.</span></span>         |
|<span data-ttu-id="73247-184">Debug-0-s2790420889. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-184">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="73247-185">Enthält Informationen zum Medien Agenten, einschließlich der Rendering-Qualität.</span><span class="sxs-lookup"><span data-stu-id="73247-185">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="73247-186">tscalling-0-2061129496. Blog</span><span class="sxs-lookup"><span data-stu-id="73247-186">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="73247-187">Zeichnet Ereignisse in der TS-Aufruf-API auf.</span><span class="sxs-lookup"><span data-stu-id="73247-187">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="73247-188">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="73247-188">Desktop logs</span></span>
---------------------

<span data-ttu-id="73247-p107">Desktopprotokolle, auch bekannt unter Bootstrapper-Protokolle, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser erstellt werden. Wie Medienprotokolle werden diese Protokolle nur auf Anforderung von Microsoft benötigt. Die Protokolle sind textbasiert und können mit jedem Texteditor von oben nach unten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="73247-p107">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="73247-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="73247-192">Windows:</span></span>

1.  <span data-ttu-id="73247-193">Klicken Sie mit der rechten Maustaste auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="73247-193">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="73247-194">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="73247-194">Mac OsX:</span></span>

1.  <span data-ttu-id="73247-195">Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**</span><span class="sxs-lookup"><span data-stu-id="73247-195">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="73247-196">Linux</span><span class="sxs-lookup"><span data-stu-id="73247-196">Linux:</span></span>

1.  <span data-ttu-id="73247-197">Klicken Sie auf das **Microsoft Teams** -Symbol in der Taskleiste, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="73247-197">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="73247-198">Client</span><span class="sxs-lookup"><span data-stu-id="73247-198">Client</span></span> |<span data-ttu-id="73247-199">Speicherort</span><span class="sxs-lookup"><span data-stu-id="73247-199">Location</span></span> |
|---------|---------|
|<span data-ttu-id="73247-200">Windows</span><span class="sxs-lookup"><span data-stu-id="73247-200">Windows</span></span>     |<span data-ttu-id="73247-201">% APPDATA% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="73247-201">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="73247-202">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="73247-202">Mac OSX</span></span>     |<span data-ttu-id="73247-203">~/Library/Application-Unterstützung/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="73247-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="73247-204">Linux</span><span class="sxs-lookup"><span data-stu-id="73247-204">Linux</span></span>       |<span data-ttu-id="73247-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="73247-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="73247-206">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="73247-206">Related topics</span></span>

[<span data-ttu-id="73247-207">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="73247-207">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

