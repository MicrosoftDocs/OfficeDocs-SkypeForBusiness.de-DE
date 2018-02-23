---
title: Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erhalten Sie Informationen zu den von Microsoft Teams erstellten Debug-, Medien- und Desktopprotokollen, zu deren Speicherort und wie diese für die Problembehandlung eingesetzt werden können."
appliesto:
- Microsoft Teams
ms.openlocfilehash: bef400cd5838848a0eb25f709e930611fac9ed6d
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="7c489-103">Verwenden von Protokolldateien bei der Problembehandlung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c489-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="7c489-104">Es gibt drei Typen von automatisch vom Client erstellten Protokolldateien, die zur Problembehandlung in Microsoft Teams eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="7c489-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="7c489-105">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="7c489-105">Debug logs</span></span>

-   <span data-ttu-id="7c489-106">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="7c489-106">Media logs</span></span>

-   <span data-ttu-id="7c489-107">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="7c489-107">Desktop logs</span></span>

<span data-ttu-id="7c489-p101">Beim Erstellen einer Supportanfrage beim Microsoft-Support fordert Sie der Supportmitarbeiter zur Einreichung von Debugprotokollen auf. Wenn Sie diese Protokolle vor dem Erstellen der Supportanfrage zur Hand haben, kann das Problem von Microsoft schneller behoben werden. Medien- oder Desktopprotokolle werden nur auf Anforderung von Microsoft benötigt.</span><span class="sxs-lookup"><span data-stu-id="7c489-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="7c489-p102">In der folgenden Tabelle werden verschiedene Clients und die jeweils zugehörigen Protokolle aufgeführt. Protokolldateien sind in den für den Client und das Betriebssystem spezifischen Verzeichnissen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7c489-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="7c489-113">Client</span><span class="sxs-lookup"><span data-stu-id="7c489-113">Client</span></span> |<span data-ttu-id="7c489-114">Debug</span><span class="sxs-lookup"><span data-stu-id="7c489-114">Debug</span></span>|<span data-ttu-id="7c489-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="7c489-115">Desktop</span></span>|<span data-ttu-id="7c489-116">Medien</span><span class="sxs-lookup"><span data-stu-id="7c489-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="7c489-117">Web</span><span class="sxs-lookup"><span data-stu-id="7c489-117">Web</span></span>    |<span data-ttu-id="7c489-118">X</span><span class="sxs-lookup"><span data-stu-id="7c489-118">X</span></span>         |-         |-         |
|<span data-ttu-id="7c489-119">Windows</span><span class="sxs-lookup"><span data-stu-id="7c489-119">Windows</span></span>     |<span data-ttu-id="7c489-120">X</span><span class="sxs-lookup"><span data-stu-id="7c489-120">X</span></span>         |<span data-ttu-id="7c489-121">X</span><span class="sxs-lookup"><span data-stu-id="7c489-121">X</span></span>         |<span data-ttu-id="7c489-122">X</span><span class="sxs-lookup"><span data-stu-id="7c489-122">X</span></span>         |
|<span data-ttu-id="7c489-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7c489-123">Mac OSX</span></span>     |<span data-ttu-id="7c489-124">X</span><span class="sxs-lookup"><span data-stu-id="7c489-124">X</span></span>         |<span data-ttu-id="7c489-125">X</span><span class="sxs-lookup"><span data-stu-id="7c489-125">X</span></span>         |<span data-ttu-id="7c489-126">X</span><span class="sxs-lookup"><span data-stu-id="7c489-126">X</span></span>         |
|<span data-ttu-id="7c489-127">iOS</span><span class="sxs-lookup"><span data-stu-id="7c489-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="7c489-128">Android</span><span class="sxs-lookup"><span data-stu-id="7c489-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="7c489-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="7c489-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="7c489-130">Eine vollständige Liste der unterstützten Betriebssystem und Browser finden Sie in den folgenden [Häufig gestellten Fragen zu Microsoft Teams](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc).</span><span class="sxs-lookup"><span data-stu-id="7c489-130">For a complete list of supported operating systems and browsers, reference the following [Microsoft Teams FAQ](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc).</span></span>

<a name="debug-logs"></a><span data-ttu-id="7c489-131">Debugprotokolle</span><span class="sxs-lookup"><span data-stu-id="7c489-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="7c489-p103">Dies sind die üblichsten und für Microsoft Teams-Supportfälle erforderlichen Protokolle. Debugprotokolle werden von den Windows- und Mac-Desktopclients sowie von browserbasierten Clients erstellt. Diese Protokolle sind textbasiert und werden von unten nach oben gelesen. Sie können mit einem textbasierten Editor gelesen werden, und neue Protokolle werden bei der Anmeldung beim Client erstellt.</span><span class="sxs-lookup"><span data-stu-id="7c489-p103">These are the most common logs and are required for all Microsoft support cases. Debug logs are produced by the Window and Mac desktop clients, as well as browser based clients. The logs are text based and are read from the bottom up. They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="7c489-136">Debugprotokolle zeigen die folgenden Datenflüsse:</span><span class="sxs-lookup"><span data-stu-id="7c489-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="7c489-137">Anmeldung</span><span class="sxs-lookup"><span data-stu-id="7c489-137">Login</span></span>

-   <span data-ttu-id="7c489-138">Verbindungsanfragen an Dienste auf mittlerer Ebene </span><span class="sxs-lookup"><span data-stu-id="7c489-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="7c489-139">Anruf/Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="7c489-139">Call/conversation</span></span>

<span data-ttu-id="7c489-140">Die Debugprotokolle werden unter Verwendung der folgenden für das jeweilige Betriebssystem spezifischen Methoden erstellt:</span><span class="sxs-lookup"><span data-stu-id="7c489-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="7c489-141">Windows:</span><span class="sxs-lookup"><span data-stu-id="7c489-141">Windows:</span></span>

    1.  <span data-ttu-id="7c489-142">Klicken Sie mit der rechten Maustaste auf **das Microsoft Teams-Symbol im** Infobereich Ihrer Anwendung, und wählen Sie **Protokolle abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="7c489-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="7c489-143">Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**</span><span class="sxs-lookup"><span data-stu-id="7c489-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="7c489-144">Tastenkombination: STRG+ALT+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="7c489-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="7c489-145">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="7c489-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="7c489-146">Auswählen von **Protokolle abrufen** aus dem Pulldownmenü **Hilfe**</span><span class="sxs-lookup"><span data-stu-id="7c489-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="7c489-147">Tastenkombination: WAHLTASTE+BEFEHLSTASTE+UMSCHALT+1</span><span class="sxs-lookup"><span data-stu-id="7c489-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="7c489-148">Die Debugprotokolle werden automatisch in die folgenden Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="7c489-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="7c489-149">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="7c489-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="7c489-150">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="7c489-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="7c489-151">Browser: Sie werden zum Speichern des Debugprotokolls in das Standardverzeichnis aufgefordert</span><span class="sxs-lookup"><span data-stu-id="7c489-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="7c489-152">Medienprotokolle</span><span class="sxs-lookup"><span data-stu-id="7c489-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="7c489-p104">Medienprotokolle enthalten Diagnosedaten zu Audio, Video und Bildschirmfreigabe Sie sind für Supportfälle nur nach Aufforderung erforderlich und können nur von Microsoft geprüft werden. In der folgenden Tabelle wird der Protokollspeicherort aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7c489-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="7c489-156">Client</span><span class="sxs-lookup"><span data-stu-id="7c489-156">Client</span></span> |<span data-ttu-id="7c489-157">Speicherort</span><span class="sxs-lookup"><span data-stu-id="7c489-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="7c489-158">Windows</span><span class="sxs-lookup"><span data-stu-id="7c489-158">Windows</span></span>     |<span data-ttu-id="7c489-159">%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="7c489-159">%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="7c489-160">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7c489-160">Mac OSX</span></span>     |<span data-ttu-id="7c489-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="7c489-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="7c489-162">Desktopprotokolle</span><span class="sxs-lookup"><span data-stu-id="7c489-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="7c489-p105">Desktopprotokolle, auch bekannt unter Bootstrapper-Protokolle, enthalten Protokolldaten, die zwischen dem Desktopclient und dem Browser erstellt werden. Wie Medienprotokolle werden diese Protokolle nur auf Anforderung von Microsoft benötigt. Die Protokolle sind textbasiert und können mit jedem Texteditor von oben nach unten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="7c489-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="7c489-166">Client</span><span class="sxs-lookup"><span data-stu-id="7c489-166">Client</span></span> |<span data-ttu-id="7c489-167">Speicherort</span><span class="sxs-lookup"><span data-stu-id="7c489-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="7c489-168">Windows</span><span class="sxs-lookup"><span data-stu-id="7c489-168">Windows</span></span>     |<span data-ttu-id="7c489-169">%appdata%\Roaming\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="7c489-169">%appdata%\Roaming\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="7c489-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7c489-170">Mac OSX</span></span>     |<span data-ttu-id="7c489-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="7c489-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
