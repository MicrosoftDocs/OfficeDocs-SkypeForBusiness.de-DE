---
title: Beziehen von Clients für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/27/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara; vichau
localization_priority: Normal
description: Hier erfahren Sie, wie Sie die verschiedenen verfügbaren Microsoft Teams-Clients für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Phone) verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 579bc0290c8375adf23a17aa8121fb7a8d363718
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="ef54e-103">Beziehen von Clients für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ef54e-103">Get clients for Microsoft Teams</span></span> 
===========================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ef54e-p101">Microsoft Teams-Clients sind für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Phone) verfügbar. Alle diese Clients erfordern eine aktive Internetverbindung. Ein Offlinemodus wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ef54e-p101">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android, iOS, and Windows Phone). These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="web-client"></a><span data-ttu-id="ef54e-106">Webclient</span><span class="sxs-lookup"><span data-stu-id="ef54e-106">Web client</span></span> 
----------

<span data-ttu-id="ef54e-107">WebClient ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) ist ein vollständiger, funktionsfähige Client, der aus einer Vielzahl von Browsern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ef54e-107">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="ef54e-108">Webclient unterstützt Anruf- und Besprechungen mithilfe von WebRTC, damit es kein Plugin ist oder herunterladen, die zum Ausführen von Teams in einem Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="ef54e-108">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="ef54e-109">Der Browser muss für Drittanbieter-Cookies konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ef54e-109">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="ef54e-110">Der Webclient führt die Erkennung des Clientbrowsers Version beim Herstellen einer Verbindung mit [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) und eine nicht unterstützte Browserversion erkannt wird, blockieren Sie den Zugriff auf die Weboberfläche und wird empfohlen, dass der Benutzer den Desktopclient oder mobilen app herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ef54e-110">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) and if an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="desktop-client"></a><span data-ttu-id="ef54e-111">Desktop-client</span><span class="sxs-lookup"><span data-stu-id="ef54e-111">Desktop client</span></span>
--------------

<span data-ttu-id="ef54e-112">Der Microsoft-Teams Desktopclient ist eine eigenständige Anwendung und derzeit kein Bestandteil von Office Pro Plus.</span><span class="sxs-lookup"><span data-stu-id="ef54e-112">The Microsoft Teams desktop client is a standalone application and currently not part of Office Pro Plus.</span></span> <span data-ttu-id="ef54e-113">Teams ist für Windows (7 +), 32-Bit- und 64-Bit-Versionen und Mac OS (10.10. +) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ef54e-113">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and MacOS (10.10+).</span></span> <span data-ttu-id="ef54e-114">Unter Windows-Teams erfordert .NET Framework 4.5 oder höher. Das Installationsprogramm Teams bietet es für Sie installieren, wenn Sie nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ef54e-114">On Windows, Teams requires .NET framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="ef54e-115">Desktop-Clients unterstützen Echtzeitkommunikation (Audio-, Video- und Content Freigabe) Team Besprechungen, Gruppe aufrufende und privaten Angebot Anrufe.</span><span class="sxs-lookup"><span data-stu-id="ef54e-115">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="ef54e-116">Desktop-Clients können heruntergeladen und installiert werden durch Endbenutzer direkt aus [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) Wenn sie die entsprechenden lokalen Berechtigungen verfügen (Administratorrechte ist nicht erforderlich, den Teams-Client auf einem PC zu installieren, aber sind erforderlich für Mac).</span><span class="sxs-lookup"><span data-stu-id="ef54e-116">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="ef54e-117">IT-Administratoren können ihre bevorzugte Methode für die Verteilung der Installationsdateien an die Computer in ihrer Organisation auswählen, beispielsweise System Center Configuration Manager (Windows) oder Casper Suite (MacOS).</span><span class="sxs-lookup"><span data-stu-id="ef54e-117">IT admins can choose their preferred method to distribute the installation files to machines in their organization such as System Center Configuration Manager (Windows) or Casper Suite (MacOS).</span></span> <span data-ttu-id="ef54e-118">Wenn Sie die MSI-Paket für Windows-Verteilung erhalten möchten, finden Sie unter [Installieren von Microsoft-Teams verwenden MSI-Datei](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="ef54e-118">To get the MSI Package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ef54e-119">Die Verteilung des Clients über diese Mechanismen ist nur für die anfängliche Installation von Microsoft Team-Clients gedacht, nicht für zukünftige Updates.</span><span class="sxs-lookup"><span data-stu-id="ef54e-119">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>


#### <a name="windows"></a><span data-ttu-id="ef54e-120">Windows</span><span class="sxs-lookup"><span data-stu-id="ef54e-120">Windows</span></span>

<span data-ttu-id="ef54e-p105">Für die Microsoft Teams-Installation unter Windows können Installationsprogramme mit 32-Bit- und 64-Bit-Architektur heruntergeladen werden. Die Architektur sollte mit der des Betriebssystems übereinstimmen und wird beim Onlinedownload standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ef54e-p105">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture. The architecture should match that of the OS, which is what the online download defaults to.</span></span>



> [!NOTE]
> <span data-ttu-id="ef54e-123">Die Architektur (32-Bit oder 64-Bit) von Microsoft Teams ist unabhängig von der Architektur der installierten Office-Version.</span><span class="sxs-lookup"><span data-stu-id="ef54e-123">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Office that is installed.</span></span>

<span data-ttu-id="ef54e-p106">Der Windows-Client wird im Ordner „AppData“ im Profil des Benutzers bereitgestellt. Durch die Bereitstellung im lokalen Profil des Benutzers kann der Client installiert werden, ohne dass erhöhte Rechte erforderlich sind. Der Windows-Client wird an den folgenden Speicherorten installiert:</span><span class="sxs-lookup"><span data-stu-id="ef54e-p106">The Windows client is deployed to the AppData folder located in the user’s profile. Deploying to the user’s local profile allows the client to be installed without requiring elevated rights. The Windows client is installed in the following locations:</span></span>

-   <span data-ttu-id="ef54e-127">%appdata%\\local\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="ef54e-127">%appdata%\\local\\Microsoft\\Teams</span></span>

-   <span data-ttu-id="ef54e-128">%appdata%\\roaming\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="ef54e-128">%appdata%\\roaming\\Microsoft\\Teams</span></span>

<span data-ttu-id="ef54e-p107">Wenn Benutzer erstmals mit dem Microsoft Teams-Client einen Anruf einleiten, sehen sie möglicherweise eine Warnung mit den Einstellungen der Windows-Firewall, in der sie aufgefordert werden, die Kommunikation zuzulassen. Die Benutzer können angewiesen werden, diese Meldung zu ignorieren, da der Anruf auch dann funktioniert, wenn die Warnung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ef54e-p107">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication. Users may be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Screenshot des Dialogfelds „Windows-Sicherheitshinweis“](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> <span data-ttu-id="ef54e-p108">Die Konfiguration der Windows-Firewall wird auch dann geändert, wenn die Eingabeaufforderung durch Auswählen von „Abbrechen“ geschlossen wird. Zwei eingehende Regeln für „teams.exe“ werden mit der Aktion „Blockieren“ für die Protokolle TCP und UDP erstellt.</span><span class="sxs-lookup"><span data-stu-id="ef54e-p108">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

#### <a name="mac"></a><span data-ttu-id="ef54e-134">Mac</span><span class="sxs-lookup"><span data-stu-id="ef54e-134">Mac</span></span>

<span data-ttu-id="ef54e-135">Microsoft stellt auch eine DMG-Installationsdatei für Mac OS X-Computer bereit.</span><span class="sxs-lookup"><span data-stu-id="ef54e-135">Microsoft also provides a DMG installation file for Mac OSX computers.</span></span> <span data-ttu-id="ef54e-136">Zum Installieren des Mac-Clients ist Administratorzugriff erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ef54e-136">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="ef54e-137">Der Mac OS X-Client wird im Ordner „/Applications“ installiert.</span><span class="sxs-lookup"><span data-stu-id="ef54e-137">The Mac OSX client is installed to the /Applications folder.</span></span>


<a name="mobile-clients"></a><span data-ttu-id="ef54e-138">Mobile Clients</span><span class="sxs-lookup"><span data-stu-id="ef54e-138">Mobile clients</span></span>
--------------

<span data-ttu-id="ef54e-p110">Die mobilen Microsoft Teams-Apps sind für Android, iOS und Windows Phone verfügbar und richten sich an Benutzer, die sich unterwegs an chatbasierten Unterhaltungen beteiligen möchten. Peer-zu-Peer-Audioanrufe sind ebenfalls möglich. Sie finden die mobilen Apps im jeweiligen mobilen Store: Google Play, Apple App Store und Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ef54e-p110">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls. For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span>

<span data-ttu-id="ef54e-141">Unterstützte mobile Plattformen für mobile Microsoft Teams-Apps:</span><span class="sxs-lookup"><span data-stu-id="ef54e-141">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="ef54e-142">**Android**: 4.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="ef54e-142">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="ef54e-143">**iOS**: 10.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="ef54e-143">**iOS**: 10.0 or later</span></span>

-   <span data-ttu-id="ef54e-144">**Windows Phone**: Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="ef54e-144">**Windows Phone**: Windows 10 Mobile</span></span>

<span data-ttu-id="ef54e-145">Mobile Apps werden nur über den jeweiligen App Store für ihre mobile Plattform verteilt und aktualisiert. Sie können nicht über MDM-Lösungen (Mobile Device Management, mobile Geräteverwaltung) verteilt oder quergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="ef54e-145">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="ef54e-147">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="ef54e-147">Decision Point</span></span>         |<span data-ttu-id="ef54e-148">Gelten Einschränkungen, die Benutzer daran hindern, den entsprechenden Microsoft Teams-Client auf ihren Geräten zu installieren?</span><span class="sxs-lookup"><span data-stu-id="ef54e-148">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="ef54e-150">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ef54e-150">Next Steps</span></span>         |<span data-ttu-id="ef54e-p111">Wenn Ihre Organisation Softwareinstallationen einschränkt, stellen Sie sicher, dass dieser Prozess mit Microsoft Teams kompatibel ist. Hinweis: Administratorrechte sind zum Installieren von Clients auf einem PC nicht erforderlich, auf einem Mac jedoch sind sie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ef54e-p111">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="ef54e-153"><span id="_Hlk477176062" class="anchor"></span>  Entscheidungspunkt   Gelten Einschränkungen, die Benutzer daran hindern, den entsprechenden Microsoft Teams-Client auf ihren Geräten zu installieren?</span><span class="sxs-lookup"><span data-stu-id="ef54e-153"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="ef54e-154">Verwaltung von Clientupdates</span><span class="sxs-lookup"><span data-stu-id="ef54e-154">Client update management</span></span>
------------------------

<span data-ttu-id="ef54e-p112">Clients werden zurzeit automatisch vom Microsoft Teams-Dienst aktualisiert, ohne dass der Eingriff eines IT-Administrators erforderlich ist. Wenn ein Update verfügbar ist, lädt der Client das Update automatisch herunter, und wenn sich die App seit einiger Zeit im Leerlauf befindet, wird der Updateprozess gestartet.</span><span class="sxs-lookup"><span data-stu-id="ef54e-p112">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="ef54e-157">Clientseitige Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="ef54e-157">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="ef54e-158">Zurzeit sind keine unterstützten Optionen zum Konfigurieren des Clients durch den Mandantenadministrator, PowerShell, Gruppenrichtlinienobjekte oder die Registrierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ef54e-158">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="ef54e-159">Benachrichtigungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ef54e-159">Notification settings</span></span>
----------------------------

<span data-ttu-id="ef54e-p113">Zurzeit sind keine Optionen verfügbar, mit denen IT-Administratoren clientseitige Benachrichtigungseinstellungen konfigurieren können. Alle Benachrichtigungsoptionen werden von den Benutzern festgelegt. Die folgende Abbildung zeigt die Standardclienteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ef54e-p113">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![Screenshot der Benachrichtigungseinstellungen](media/Get_clients_for_Microsoft_Teams_image6.png)
