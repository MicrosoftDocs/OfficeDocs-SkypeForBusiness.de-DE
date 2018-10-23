---
title: Beziehen von Clients für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: vichau, majafry
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die verschiedenen verfügbaren Microsoft Teams-Clients für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Phone) verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a24f4ba3c9470827c8a73bf8ac234cf7ae8467e8
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2018
ms.locfileid: "25372788"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="5a761-103">Beziehen von Clients für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a761-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="5a761-104">Microsoft-Teams, hat die Clients verfügbar für desktop (Windows und Mac), Web und mobile (Android-, IOS- und Windows Phone).</span><span class="sxs-lookup"><span data-stu-id="5a761-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android,  iOS, and Windows Phone).</span></span> <span data-ttu-id="5a761-105">Alle diese Clients erfordern eine aktive Internetverbindung. Ein Offlinemodus wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a761-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="desktop-client"></a><span data-ttu-id="5a761-106">Desktop-client</span><span class="sxs-lookup"><span data-stu-id="5a761-106">Desktop client</span></span>
--------------

> [!Tip]
> <span data-ttu-id="5a761-107">Sehen Sie sich die folgenden Sitzung Informationen zu den Vorteilen der Windows-Desktop Client, wie es geplant und wie diese bereitgestellt: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="5a761-107">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="5a761-108">Der Microsoft-Teams Desktopclient ist eine eigenständige Anwendung und derzeit kein Bestandteil von Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="5a761-108">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="5a761-109">Teams ist für Windows (7 +), 32-Bit- und 64-Bit-Versionen und Mac OS (10.10. +) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5a761-109">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="5a761-110">Unter Windows-Teams erfordert .NET Framework 4.5 oder höher. Das Installationsprogramm Teams bietet es für Sie installieren, wenn Sie nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5a761-110">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="5a761-111">Desktop-Clients unterstützen Echtzeitkommunikation (Audio-, Video- und Content Freigabe) Team Besprechungen, Gruppe aufrufende und privaten Angebot Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5a761-111">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="5a761-112">Desktop-Clients können heruntergeladen und installiert werden durch Endbenutzer direkt aus [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) Wenn sie die entsprechenden lokalen Berechtigungen verfügen (Administratorrechte ist nicht erforderlich, den Teams-Client auf einem PC zu installieren, aber sind erforderlich für Mac).</span><span class="sxs-lookup"><span data-stu-id="5a761-112">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="5a761-113">IT-Administratoren können ihre bevorzugte Methode zum Verteilen der Installationsdateien auf Computern in ihrer Organisation, beispielsweise von System Center Configuration Manager (Windows) oder Jamf Pro (Mac OS) auswählen.</span><span class="sxs-lookup"><span data-stu-id="5a761-113">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="5a761-114">Wenn das MSI-Paket für die Windows-Verteilung erhalten möchten, finden Sie unter [Installieren von Microsoft-Teams verwenden MSI-Datei](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="5a761-114">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5a761-115">Die Verteilung des Clients über diese Mechanismen ist nur für die anfängliche Installation von Microsoft Team-Clients gedacht, nicht für zukünftige Updates.</span><span class="sxs-lookup"><span data-stu-id="5a761-115">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="5a761-116">Windows</span><span class="sxs-lookup"><span data-stu-id="5a761-116">Windows</span></span>

<span data-ttu-id="5a761-117">Die Microsoft-Teams, Installation für Windows bietet herunterladbare Installer in 32-Bit- und 64-Bit-Architektur.</span><span class="sxs-lookup"><span data-stu-id="5a761-117">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="5a761-118">Die Architektur (32-Bit im Vergleich zu 64-Bit) von Microsoft-Teams, ist der Architektur von Windows und Office-Installation unabhängig.</span><span class="sxs-lookup"><span data-stu-id="5a761-118">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="5a761-119">Der Windows-Client wird in den Anwendungsdaten-Ordner befindet sich im Profil des Benutzers bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5a761-119">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="5a761-120">Bereitstellen von lokalen Profil des Benutzers ermöglicht dem Client installiert werden soll, ohne dass mit erhöhten Rechten Rechte.</span><span class="sxs-lookup"><span data-stu-id="5a761-120">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="5a761-121">Der Windows-Client nutzt die folgenden Speicherorten:</span><span class="sxs-lookup"><span data-stu-id="5a761-121">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="5a761-122">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="5a761-122">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="5a761-123">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span><span class="sxs-lookup"><span data-stu-id="5a761-123">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span></span>

- <span data-ttu-id="5a761-124">Anwendungsdaten %\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="5a761-124">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="5a761-125">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="5a761-125">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="5a761-126">Wenn Benutzer einen Anruf über den Client für Microsoft-Teams zum ersten Mal starten, bemerken sie möglicherweise eine Warnung mit den Einstellungen der Windows-Firewall mit der Aufforderung für Benutzer, um die Kommunikation zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5a761-126">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="5a761-127">Benutzer möglicherweise aufgefordert, diese Meldung ignorieren, da der Anruf wird arbeiten, auch wenn die Warnung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="5a761-127">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Screenshot des Dialogfelds „Windows-Sicherheitshinweis“](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="5a761-p106">Die Konfiguration der Windows-Firewall wird auch dann geändert, wenn die Eingabeaufforderung durch Auswählen von „Abbrechen“ geschlossen wird. Zwei eingehende Regeln für „teams.exe“ werden mit der Aktion „Blockieren“ für die Protokolle TCP und UDP erstellt.</span><span class="sxs-lookup"><span data-stu-id="5a761-p106">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="5a761-131">Mac</span><span class="sxs-lookup"><span data-stu-id="5a761-131">Mac</span></span>

<span data-ttu-id="5a761-132">Mac-Benutzer können Teams mithilfe einer Installation Paketdatei für Mac OS-Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="5a761-132">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="5a761-133">Zum Installieren des Mac-Clients ist Administratorzugriff erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5a761-133">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="5a761-134">Mac OS-Client wird in den Ordner/Programme installiert.</span><span class="sxs-lookup"><span data-stu-id="5a761-134">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="5a761-135">Installieren von Teams mithilfe der Paketdatei</span><span class="sxs-lookup"><span data-stu-id="5a761-135">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="5a761-136">Die [Downloadseite für Teams](https://teams.microsoft.com/downloads)unter **Mac**, klicken Sie auf **herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="5a761-136">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="5a761-137">Klicken Sie mit der Doppelklicken auf die Paketdatei.</span><span class="sxs-lookup"><span data-stu-id="5a761-137">Double click the PKG file.</span></span>
3. <span data-ttu-id="5a761-138">Führen Sie den Installations-Assistenten, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5a761-138">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="5a761-139">Teams werden Ordner/Programme installiert werden.</span><span class="sxs-lookup"><span data-stu-id="5a761-139">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="5a761-140">Es ist eine computerweiten-Installation.</span><span class="sxs-lookup"><span data-stu-id="5a761-140">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="5a761-141">Während der Installation werden die PKG-Admin-Anmeldeinformationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5a761-141">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="5a761-142">Der Benutzer muss die Administratoranmeldeinformationen, unabhängig davon, ob der Benutzer Administrator ist eingeben</span><span class="sxs-lookup"><span data-stu-id="5a761-142">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="5a761-143">Wenn ein Benutzer derzeit eine DMG-Installation von Teams hat und Ersetzen Sie es mit der Installation PKG möchte, sollte der Benutzer:</span><span class="sxs-lookup"><span data-stu-id="5a761-143">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="5a761-144">Beenden Sie die app Teams.</span><span class="sxs-lookup"><span data-stu-id="5a761-144">Exit the Teams app.</span></span>
2. <span data-ttu-id="5a761-145">Deinstallieren Sie die app Teams.</span><span class="sxs-lookup"><span data-stu-id="5a761-145">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="5a761-146">Installieren der Paketdatei.</span><span class="sxs-lookup"><span data-stu-id="5a761-146">Install the PKG file.</span></span>

<span data-ttu-id="5a761-147">Verwaltete Bereitstellung von Teams können IT-Administratoren die Installationsdateien alle Macs in ihrer Organisation, beispielsweise Jamf Pro verteilen.</span><span class="sxs-lookup"><span data-stu-id="5a761-147">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="5a761-148">Wenn Sie Probleme beim Installieren von der PKG auftreten, wollen wir uns kennen.</span><span class="sxs-lookup"><span data-stu-id="5a761-148">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="5a761-149">Klicken Sie im Bereich am Ende dieses Artikels **Feedback** auf **Feedback zum Produkt**.</span><span class="sxs-lookup"><span data-stu-id="5a761-149">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="5a761-150">Webclient</span><span class="sxs-lookup"><span data-stu-id="5a761-150">Web client</span></span> 
----------

<span data-ttu-id="5a761-151">WebClient ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) ist ein vollständiger, funktionsfähige Client, der aus einer Vielzahl von Browsern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5a761-151">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="5a761-152">Webclient unterstützt Anruf- und Besprechungen mithilfe von WebRTC, damit es kein Plugin ist oder herunterladen, die zum Ausführen von Teams in einem Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="5a761-152">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="5a761-153">Der Browser muss für Drittanbieter-Cookies konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5a761-153">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="5a761-154">Der Webclient führt die Erkennung des Clientbrowsers Version beim Herstellen einer Verbindung mit [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="5a761-154">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="5a761-155">Wenn eine nicht unterstützte Browserversion erkannt wurde, wird es blockieren Sie den Zugriff auf die Weboberfläche und wird empfohlen, dass der Benutzer den Desktopclient oder mobilen app herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5a761-155">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="5a761-156">Mobile Clients</span><span class="sxs-lookup"><span data-stu-id="5a761-156">Mobile clients</span></span>
--------------

<span data-ttu-id="5a761-157">Die Microsoft-Teams, mobilen apps stehen für Android und iOS-Go Benutzer, die Teilnahme an Unterhaltungen Chat-basierte abgestimmt werden und Peer-zu-Peer-Audioanrufe zulassen.</span><span class="sxs-lookup"><span data-stu-id="5a761-157">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="5a761-158">Mobiler apps finden Sie die entsprechenden mobilen Speicher Google wiedergeben und im Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="5a761-158">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="5a761-159">Die Windows Phone-App wurde zurückgezogen 20 Juli 2018 finden Sie [hier](https://support.microsoft.com/en-us/help/4230833/windows-phone-app-for-microsoft-teams-is-retiring) Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="5a761-159">The Windows Phone App was retired July 20, 2018 see [here](https://support.microsoft.com/en-us/help/4230833/windows-phone-app-for-microsoft-teams-is-retiring) for more information.</span></span>

<span data-ttu-id="5a761-160">Unterstützte mobile Plattformen für mobile Microsoft Teams-Apps:</span><span class="sxs-lookup"><span data-stu-id="5a761-160">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="5a761-161">**Android**: 4.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="5a761-161">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="5a761-162">**iOS**: 10.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="5a761-162">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="5a761-163">Die mobile Version muss an die Öffentlichkeit in Reihenfolge für Teams erwartungsgemäß verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="5a761-163">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="5a761-164">Mobile Apps werden nur über den jeweiligen App Store für ihre mobile Plattform verteilt und aktualisiert. Sie können nicht über MDM-Lösungen (Mobile Device Management, mobile Geräteverwaltung) verteilt oder quergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="5a761-164">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="5a761-166">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="5a761-166">Decision Point</span></span>         |<span data-ttu-id="5a761-167">Gelten Einschränkungen, die Benutzer daran hindern, den entsprechenden Microsoft Teams-Client auf ihren Geräten zu installieren?</span><span class="sxs-lookup"><span data-stu-id="5a761-167">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="5a761-169">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5a761-169">Next Steps</span></span>         |<span data-ttu-id="5a761-p114">Wenn Ihre Organisation Softwareinstallationen einschränkt, stellen Sie sicher, dass dieser Prozess mit Microsoft Teams kompatibel ist. Hinweis: Administratorrechte sind zum Installieren von Clients auf einem PC nicht erforderlich, auf einem Mac jedoch sind sie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5a761-p114">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="5a761-172"><span id="_Hlk477176062" class="anchor"></span>  Entscheidungspunkt   Gelten Einschränkungen, die Benutzer daran hindern, den entsprechenden Microsoft Teams-Client auf ihren Geräten zu installieren?</span><span class="sxs-lookup"><span data-stu-id="5a761-172"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="5a761-173">Verwaltung von Clientupdates</span><span class="sxs-lookup"><span data-stu-id="5a761-173">Client update management</span></span>
------------------------

<span data-ttu-id="5a761-p115">Clients werden zurzeit automatisch vom Microsoft Teams-Dienst aktualisiert, ohne dass der Eingriff eines IT-Administrators erforderlich ist. Wenn ein Update verfügbar ist, lädt der Client das Update automatisch herunter, und wenn sich die App seit einiger Zeit im Leerlauf befindet, wird der Updateprozess gestartet.</span><span class="sxs-lookup"><span data-stu-id="5a761-p115">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="5a761-176">Clientseitige Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5a761-176">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="5a761-177">Zurzeit sind keine unterstützten Optionen zum Konfigurieren des Clients durch den Mandantenadministrator, PowerShell, Gruppenrichtlinienobjekte oder die Registrierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5a761-177">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="5a761-178">Benachrichtigungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="5a761-178">Notification settings</span></span>
----------------------------

<span data-ttu-id="5a761-p116">Zurzeit sind keine Optionen verfügbar, mit denen IT-Administratoren clientseitige Benachrichtigungseinstellungen konfigurieren können. Alle Benachrichtigungsoptionen werden von den Benutzern festgelegt. Die folgende Abbildung zeigt die Standardclienteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5a761-p116">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![Screenshot der Benachrichtigungseinstellungen](media/Get_clients_for_Microsoft_Teams_image6.png)
