---
title: Teams für virtualisierte Desktopinfrastruktur
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Erfahren Sie, wie Microsoft-Teams in einer virtualisierten Desktop Infrastructure (VDI)-Umgebung ausführen.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1491932206812f81843c784274ffc7ea4102ee0b
ms.sourcegitcommit: 7fe8daf07013d7c532f128a3ae3bbf51d1b2aac9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2019
ms.locfileid: "31808070"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="b8eaf-103">Teams für virtualisierte Desktopinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="b8eaf-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="b8eaf-104">Dieser Artikel beschreibt die Anforderungen und Einschränkungen für die Verwendung von Microsoft-Teams in einer virtualisierten Umgebung.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="b8eaf-105">Was ist VDI?</span><span class="sxs-lookup"><span data-stu-id="b8eaf-105">What is VDI?</span></span>

<span data-ttu-id="b8eaf-106">Virtual Desktop Infrastructure (VDI) ist Virtualisierungstechnologie, die ein desktop-Betriebssystem und Anwendungen auf einem zentralen Server in einem Rechenzentrum gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="b8eaf-107">Dies ermöglicht eine vollständig personalisierte desktop Umgebung für Benutzer mit eine zentrale Quelle vollständig gesicherte und kompatibel.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="b8eaf-108">Derzeit Teams in einer virtualisierten Umgebung mit Unterstützung für die Zusammenarbeit und Chat Funktionalität mit einem dedizierten persistent virtualisierte Computer (VM) verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="b8eaf-109">Um eine optimale Umgebung sicherzustellen, befolgen Sie die Anweisungen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="b8eaf-110">Anforderungen für Teams</span><span class="sxs-lookup"><span data-stu-id="b8eaf-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="b8eaf-111">Festlegen von Richtlinien zum Deaktivieren von aufrufen und meeting-Funktionalität in Teams</span><span class="sxs-lookup"><span data-stu-id="b8eaf-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="b8eaf-112">Die Teams aufrufen und meeting Erfahrung ist nicht für eine VDI-Umgebung (bald verfügbar) optimiert.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="b8eaf-113">Es wird empfohlen, dass Festlegen von Richtlinien auf Benutzerebene, um zu deaktivieren aufrufen und meeting-Funktionalität in Teams.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="b8eaf-114">Sie können dennoch wählen, Teams vollständig in VDI führen über die Teams-desktop-app oder Web app.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="b8eaf-115">Jedoch wird empfohlen, dass Sie die Richtlinien nicht beeinträchtigt die Benutzeroberfläche festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="b8eaf-116">Es kann einige Zeit (ein paar Stunden) für die Richtlinie ändert weitergegeben dauern.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="b8eaf-117">Wenn Sie Änderungen für ein bestimmtes Konto sofort nicht angezeigt wird, versuchen Sie erneut in ein paar Stunden.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="b8eaf-118">Beim Aufruf von Teams und Besprechungen für die Verwendung in virtuellen Umgebungen desktop optimiert sind, können Sie diese Richtlinien zurücksetzen und ermöglichen Benutzern die Verwendung von Teams, wie üblich.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="b8eaf-119">Anrufe</span><span class="sxs-lookup"><span data-stu-id="b8eaf-119">Calling</span></span>

<span data-ttu-id="b8eaf-120">Verwenden Sie die **CSTeamsCallingPolicy** -Cmdlets zum Steuerelement, ob Benutzer dürfen verwenden aufrufen und Optionen in privaten aufrufen und Gruppe chats.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="b8eaf-121">Hier wird die Liste der Einstellungen für Gruppenrichtlinien und die empfohlenen Werte.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="b8eaf-122">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="b8eaf-122">Policy name</span></span>  |<span data-ttu-id="b8eaf-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8eaf-123">Description</span></span> |<span data-ttu-id="b8eaf-124">Empfohlener Wert</span><span class="sxs-lookup"><span data-stu-id="b8eaf-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b8eaf-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="b8eaf-125">AllowCalling</span></span>    |<span data-ttu-id="b8eaf-126">Steuerelemente Interop Funktionen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="b8eaf-127">Aktivieren Sie dies ermöglicht Skype für Unternehmensbenutzer Angebot Anrufe mit Benutzern von Teams und umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="b8eaf-128">Um zu verhindern, dass Anrufe von Skype für Unternehmensbenutzer Zielseite in Teams auf False festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="b8eaf-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="b8eaf-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="b8eaf-130">Steuert, ob die Aufruf von app in der app-Leiste auf der linken Seite des Teams-Clients verfügbar ist, und gibt an, ob Benutzer Anrufe und Optionen in privaten Chat aufrufen Video finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="b8eaf-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="b8eaf-131">So entfernen Sie die app Aufrufen aus der app-Leiste auf der linken Seite des Teams und Anrufoptionen Anruf- und Video im privaten Chat entfernen auf False festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="b8eaf-132">Erstellen und Zuweisen einer Richtlinie auf aufrufenden</span><span class="sxs-lookup"><span data-stu-id="b8eaf-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="b8eaf-133">Starten Sie eine Windows PowerShell-Sitzung als Administrator an.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="b8eaf-134">Verbinden Sie mit der Online Skype-Connector.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="b8eaf-135">Anzeigen einer Liste der Anrufoptionen Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="b8eaf-136">Suchen Sie nach die Option integrierte Richtlinie, bei denen alle Richtlinien für die aufrufende deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="b8eaf-137">Es sieht folgendermaßen aus.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="b8eaf-138">Gelten Sie die Option DisallowCalling integrierten Richtlinie für alle Benutzer, die Teams in einer virtualisierten Umgebung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="b8eaf-139">Weitere Informationen zu Teams aufrufende Richtlinien finden Sie unter [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="b8eaf-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="b8eaf-140">Besprechungen</span><span class="sxs-lookup"><span data-stu-id="b8eaf-140">Meetings</span></span>

<span data-ttu-id="b8eaf-141">Verwenden Sie die **CsTeamsMeetingPolicy** -Cmdlets um zu steuern, welche Art von Besprechungen, die Benutzer erstellen können, die Features, die sie während einer Besprechung zugreifen können und die Meeting-Features, die für anonyme als auch externe Benutzer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="b8eaf-142">Hier wird die Liste der Einstellungen für Gruppenrichtlinien und die empfohlenen Werte.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="b8eaf-143">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="b8eaf-143">Policy Name</span></span> |<span data-ttu-id="b8eaf-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8eaf-144">Description</span></span>|<span data-ttu-id="b8eaf-145">Empfohlene Wert</span><span class="sxs-lookup"><span data-stu-id="b8eaf-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="b8eaf-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b8eaf-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="b8eaf-147">Bestimmt, ob ein Benutzer das Planen von privaten Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="b8eaf-148">Benutzer an der Freigabefunktion für private Konferenzen planen auf False festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="b8eaf-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b8eaf-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="b8eaf-150">Bestimmt, ob ein Benutzer das Planen von Besprechungen DDE-Kanal zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="b8eaf-151">Um zu verhindern, dass den Benutzer, Anwendungen oder Bildschirme Channel Besprechungen planen auf False festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="b8eaf-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="b8eaf-152">AllowMeetNow</span></span> |<span data-ttu-id="b8eaf-153">Bestimmt, ob ein Benutzer berechtigt ist, erstellen oder Ad-hoc-Besprechungen starten.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="b8eaf-154">Legen Sie dies auf false fest, um zu verhindern, dass den Benutzer, dass mehr Ad-hoc-Besprechungen gestartet.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="b8eaf-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="b8eaf-155">ScreenSharingMode</span></span> | <span data-ttu-id="b8eaf-156">Bestimmt den Modus, in dem ein Benutzer freigeben seines Bildschirms in Anrufe oder Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="b8eaf-157">Um zu verhindern, dass den Benutzer ihre Bildschirme Freigabe auf deaktiviert festgelegt</span><span class="sxs-lookup"><span data-stu-id="b8eaf-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="b8eaf-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="b8eaf-158">AllowIPVideo</span></span> |<span data-ttu-id="b8eaf-159">Bestimmt, ob das Video in Besprechungen oder Anrufe des Benutzers aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="b8eaf-160">Auf False festgelegt, um zu verhindern, dass den Benutzer seine Videowiedergabe Freigabe</span><span class="sxs-lookup"><span data-stu-id="b8eaf-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="b8eaf-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="b8eaf-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="b8eaf-162">Bestimmt, ob anonyme Benutzer anwählen eine PSTN-Nummer zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="b8eaf-163">Auf False festgelegt, um zu verhindern, dass anonyme Benutzer Telefonverbindung</span><span class="sxs-lookup"><span data-stu-id="b8eaf-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="b8eaf-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="b8eaf-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="b8eaf-165">Bestimmt, ob anonyme Benutzer eine Besprechung starten können.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="b8eaf-166">Auf False festgelegt, um zu verhindern, dass Benutzer beginnen einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="b8eaf-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="b8eaf-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="b8eaf-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="b8eaf-168">Bestimmt, ob ein Benutzer Besprechungen im Outlook-Desktopclient Teams planen kann.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="b8eaf-169">Auf False festgelegt, um zu verhindern, dass einen Benutzer Planen von Besprechungen im Outlook-Desktopclient Teams</span><span class="sxs-lookup"><span data-stu-id="b8eaf-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="b8eaf-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="b8eaf-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="b8eaf-171">Bestimmt, ob Teilnehmer übergeben der Steuerung Bildschirmfreigabe oder anfordern können.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="b8eaf-172">Auf False festgelegt ist, an den Benutzer zu hindern vermitteln und Anfordern der Steuerung in einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="b8eaf-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="b8eaf-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="b8eaf-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="b8eaf-174">Bestimmt, ob externe Teilnehmer übergeben der Steuerung Bildschirmfreigabe oder anfordern können.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="b8eaf-175">Auf False festgelegt, um einen externen Benutzer dazu führte, zu untersagen Anfordern der Steuerung in einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="b8eaf-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="b8eaf-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="b8eaf-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="b8eaf-177">Bestimmt, ob PowerPoint-Freigabe in einem Benutzer Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="b8eaf-178">Auf False festgelegt, um zu verhindern, dass einen Benutzer freigeben von PowerPoint-Dateien in einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="b8eaf-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="b8eaf-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="b8eaf-179">AllowWhiteboard</span></span> | <span data-ttu-id="b8eaf-180">Bestimmt, ob Whiteboard in einem Benutzer Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="b8eaf-181">Auf False festgelegt, Whiteboard in einer Besprechung nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="b8eaf-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="b8eaf-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="b8eaf-182">AllowTranscription</span></span> |<span data-ttu-id="b8eaf-183">Bestimmt, ob in Echtzeit und/oder nach dem meeting Beschriftungen und Abschriften an einen Benutzer Besprechungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="b8eaf-184">Auf False festgelegt, Umsetzung und Beschriftungen in einer Besprechung nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="b8eaf-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="b8eaf-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="b8eaf-185">AllowSharedNotes</span></span> | <span data-ttu-id="b8eaf-186">Bestimmt, ob Benutzer freigegebene Notizen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="b8eaf-187">Auf False festgelegt, um zu verhindern, dass Benutzer freigegebene Notizen</span><span class="sxs-lookup"><span data-stu-id="b8eaf-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="b8eaf-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="b8eaf-188">MediaBitRateKB</span></span> |<span data-ttu-id="b8eaf-189">Bestimmt die Medien Bitrate für Audio/Video/Anwendungsfreigabe Übertragungen an Besprechungen</span><span class="sxs-lookup"><span data-stu-id="b8eaf-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="b8eaf-190">Vorgeschlagener Wert ist 5000 (5 MB).</span><span class="sxs-lookup"><span data-stu-id="b8eaf-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="b8eaf-191">Sie können ihn auf Basis der Anforderungen Ihrer Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="b8eaf-192">Erstellen und Zuweisen einer besprechungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="b8eaf-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="b8eaf-193">Starten Sie eine Windows PowerShell-Sitzung als Administrator an.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="b8eaf-194">Verbinden Sie mit der Online Skype-Connector.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="b8eaf-195">Anzeigen einer Liste der Richtlinie Besprechungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="b8eaf-196">Suchen Sie nach die Option integrierte Richtlinie, bei denen alle Besprechungsrichtlinien deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="b8eaf-197">Es sieht folgendermaßen aus.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AlowTranscription                           : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="b8eaf-198">Gelten Sie die Option AllOff integrierten Richtlinie für alle Benutzer, die Teams in einer virtualisierten Umgebung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="b8eaf-199">Weitere Informationen zu Besprechungsrichtlinien Teams finden Sie unter [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="b8eaf-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="b8eaf-200">Anforderungen für die Virtualisierung-Anbieter</span><span class="sxs-lookup"><span data-stu-id="b8eaf-200">Virtualization provider requirements</span></span>

<span data-ttu-id="b8eaf-201">Die app Teams wurde auf führende Virtualisierung Lösungsanbieter validiert.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="b8eaf-202">Wenden Sie mit mehreren Anbietern für Land/Ihrer Region sich an Ihrer Lösungsanbieter Virtualisierung, um sicherzustellen, dass die Mindestanforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="b8eaf-203">Anforderungen für die virtuellen Computer</span><span class="sxs-lookup"><span data-stu-id="b8eaf-203">Virtual Machine requirements</span></span>

<span data-ttu-id="b8eaf-204">Mit den unterschiedlichen Arbeitslasten und der benutzeranforderungen in einer virtualisierten Umgebung ist die folgenden mindestens VM-Konfiguration empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="b8eaf-205">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8eaf-205">Parameter</span></span>  |<span data-ttu-id="b8eaf-206">Measure</span><span class="sxs-lookup"><span data-stu-id="b8eaf-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="b8eaf-207">vCPU mit</span><span class="sxs-lookup"><span data-stu-id="b8eaf-207">vCPU</span></span>    |  <span data-ttu-id="b8eaf-208">2 Kerne</span><span class="sxs-lookup"><span data-stu-id="b8eaf-208">2 cores</span></span>       |
|<span data-ttu-id="b8eaf-209">RAM</span><span class="sxs-lookup"><span data-stu-id="b8eaf-209">RAM</span></span>     |  <span data-ttu-id="b8eaf-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="b8eaf-210">4 GB</span></span>      |
|<span data-ttu-id="b8eaf-211">Speicher</span><span class="sxs-lookup"><span data-stu-id="b8eaf-211">Storage</span></span>     | <span data-ttu-id="b8eaf-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="b8eaf-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="b8eaf-213">Betriebssystemanforderungen für die virtuellen Computer</span><span class="sxs-lookup"><span data-stu-id="b8eaf-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="b8eaf-214">Die unterstützten Betriebssysteme für VM sind:</span><span class="sxs-lookup"><span data-stu-id="b8eaf-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="b8eaf-215">Windows 10 und höher</span><span class="sxs-lookup"><span data-stu-id="b8eaf-215">Windows 10 and later</span></span>
- <span data-ttu-id="b8eaf-216">Windows Server 2012 R2 und höher</span><span class="sxs-lookup"><span data-stu-id="b8eaf-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="b8eaf-217">Installieren von Teams auf VDI</span><span class="sxs-lookup"><span data-stu-id="b8eaf-217">Install Teams on VDI</span></span>

<span data-ttu-id="b8eaf-218">Hier wird der Prozess und die Tools zum Bereitstellen von Teams-desktop-app.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="b8eaf-219">Herunterladen Sie Teams MSI-Paket mit einer der folgenden Links je nach der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="b8eaf-220">Wir empfehlen die 64-Bit-Version für eine VDI VM mit einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="b8eaf-221">32-Bit-version</span><span class="sxs-lookup"><span data-stu-id="b8eaf-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="b8eaf-222">64-Bit-version</span><span class="sxs-lookup"><span data-stu-id="b8eaf-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="b8eaf-223">Führen Sie den folgenden Befehl zum Installieren der MSI-Datei für die VDI-VM (oder Abschließen der Aktualisierung).</span><span class="sxs-lookup"><span data-stu-id="b8eaf-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="b8eaf-224">Dies installiert Teams Program Files.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="b8eaf-225">Zu diesem Zeitpunkt ist das goldene Bild Setup abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="b8eaf-226">Die nächste interaktive Sitzung beginnt Teams und fordert die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="b8eaf-227">Beachten Sie, dass es nicht möglich, automatisch gestartet Teams bei der Installation von Teams auf VDI mithilfe der ALLUSER-Eigenschaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="b8eaf-228">Führen Sie den folgenden Befehl zum Deinstallieren der MSI-Datei aus der VDI VM (oder Vorbereiten der Aktualisierung).</span><span class="sxs-lookup"><span data-stu-id="b8eaf-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="b8eaf-229">Dies deinstalliert Teams aus Program Files.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="b8eaf-230">Bekannte Probleme und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b8eaf-230">Known issues and limitations</span></span>

<span data-ttu-id="b8eaf-231">Die folgenden sind Probleme und Einschränkungen für VDI-Teams bekannt.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="b8eaf-232">**Shared Session Host Typ Bereitstellungen**: Shared Session Host Typ Bereitstellungen (beispielsweise freigegebene nicht beständige VM-Konfiguration) werden nicht im Bereich.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="b8eaf-233">**Anruf- und Besprechungen**:</span><span class="sxs-lookup"><span data-stu-id="b8eaf-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="b8eaf-234">Anruf- und meeting-Szenarien sind nicht für VDI optimiert.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="b8eaf-235">Diese Szenarien führt schlecht.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="b8eaf-236">Es wird empfohlen, mithilfe von Richtlinien auf Benutzerebene, wie im Abschnitt [Festlegen von Richtlinien zum Deaktivieren der aufrufen und Funktionalität in Teams meeting](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="b8eaf-237">Die in diesem Artikel beschriebenen Richtlinien anwenden und wirkt sich auf die Möglichkeit, verwenden Sie aufrufende und Besprechungen-Funktion, die je nach den anderen Richtlinien, anderen Benutzern in Ihrer Organisation beeinträchtigen können.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="b8eaf-238">Wenn Benutzer in Ihrer Organisation nicht VDI-Clients verwenden, können Sie nicht die Richtlinien gelten.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="b8eaf-239">**Teilnehmen an Anrufe und Besprechungen, die von anderen Benutzern erstellte**: zwar Richtlinien für die Benutzer beschränken von Besprechungen erstellen, sie können immer noch an Besprechungen teilnehmen, wenn ein anderer Benutzer aus der Besprechung, Ihnen wählt.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="b8eaf-240">An diesen Besprechungen, die Möglichkeit eines Benutzers zum Freigeben von Video, hängen Whiteboard verwenden und andere Features, ob Sie diese Features verwenden TeamsMeetingPolicy deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="b8eaf-241">**Cache-Inhalten**: ist die virtuelle Umgebung, in welche Teams ausgeführt wird, nicht persistent (und Daten werden am Ende jeder Sitzung des Benutzers bereinigt), Benutzer möglicherweise Leistungseinbußen aufgrund von aktualisieren, unabhängig davon, ob der Benutzer die gleiche zugegriffen fest Inhalte in einer vorherigen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="b8eaf-242">**Clientupdates**: Teams auf VDI ist nicht vergleichbar, die nicht - VDI-Teams Clients werden automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="b8eaf-243">Sie müssen das Bild VM aktualisieren, indem Sie eine neue MSI-Datei installieren, wie im Abschnitt [Installieren Teams auf VDI](#install-teams-on-vdi) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="b8eaf-244">Sie müssen die aktuelle Version auf eine neuere Version aktualisieren deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="b8eaf-245">**Benutzerinteraktion**: Benutzeroberfläche für die Teams in einer VDI-Umgebung kann von einer nicht-VDI-Umgebung abweichen.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="b8eaf-246">Die Unterschiede können aufgrund von Richtlinieneinstellungen werden und/oder feature Support in der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="b8eaf-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="b8eaf-247">Teams bekannte Probleme, die nicht mit VDI verknüpft sind, finden Sie unter [bekannte Probleme mit Microsoft-Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b8eaf-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8eaf-248">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b8eaf-248">Related topics</span></span>

- [<span data-ttu-id="b8eaf-249">Installieren von Microsoft Teams mithilfe eines MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="b8eaf-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)