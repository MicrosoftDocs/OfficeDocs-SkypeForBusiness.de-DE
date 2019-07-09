---
title: Teams für Virtualized Desktop Infrastructure
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
description: Erfahren Sie, wie Sie Microsoft Teams in einer VDI-Umgebung (virtualisierte Desktop Infrastruktur) ausführen.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e88a5fb4e8522a94389e3bad24ddc3da8283a53
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588143"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="74d41-103">Teams für Virtualized Desktop Infrastructure</span><span class="sxs-lookup"><span data-stu-id="74d41-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="74d41-104">In diesem Artikel werden die Anforderungen und Einschränkungen für die Verwendung von Microsoft Teams in einer virtualisierten Umgebung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74d41-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="74d41-105">Was ist VDI?</span><span class="sxs-lookup"><span data-stu-id="74d41-105">What is VDI?</span></span>

<span data-ttu-id="74d41-106">Virtual Desktop Infrastructure (VDI) ist eine Virtualisierungstechnologie, die ein Desktop Betriebssystem und Anwendungen auf einem zentralen Server in einem Rechenzentrum hostet.</span><span class="sxs-lookup"><span data-stu-id="74d41-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="74d41-107">Dies ermöglicht Benutzern mit einer vollständig gesicherten und kompatiblen zentralisierten Quelle eine vollständig personalisierte Desktopoberfläche.</span><span class="sxs-lookup"><span data-stu-id="74d41-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="74d41-108">Derzeit stehen Teams in einer virtualisierten Umgebung mit Unterstützung für die Zusammenarbeit und Chatfunktionalität mit einem dedizierten beständigen virtualisierten Computer (VM) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="74d41-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="74d41-109">Befolgen Sie die Anleitungen in diesem Artikel, um eine optimale Benutzererfahrung zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="74d41-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="74d41-110">Anforderungen für Teams</span><span class="sxs-lookup"><span data-stu-id="74d41-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="74d41-111">Einrichten von Richtlinien zum Deaktivieren von Anruf-und Besprechungsfunktionen in Teams</span><span class="sxs-lookup"><span data-stu-id="74d41-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="74d41-112">Die Anruf-und Besprechungs Erfahrung von Teams ist nicht für eine VDI-Umgebung optimiert (in Kürze verfügbar).</span><span class="sxs-lookup"><span data-stu-id="74d41-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="74d41-113">Wir empfehlen, Richtlinien auf Benutzerebene zu definieren, um die Anruf-und Besprechungsfunktionen in Teams zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="74d41-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="74d41-114">Sie können weiterhin Teams mit der Desktop-App "Teams" oder der Web-App in VDI vollständig in VDI ausführen.</span><span class="sxs-lookup"><span data-stu-id="74d41-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="74d41-115">Es wird jedoch empfohlen, die Richtlinien festzulegen, um eine Gefährdung der Benutzerfreundlichkeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="74d41-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="74d41-116">Es kann einige Zeit dauern (einige Stunden), bis die Richtlinienänderungen übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="74d41-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="74d41-117">Wenn Änderungen für ein bestimmtes Konto nicht sofort angezeigt werden, versuchen Sie es in ein paar Stunden noch einmal.</span><span class="sxs-lookup"><span data-stu-id="74d41-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="74d41-118">Wenn die Anrufe und Besprechungen von Teams für die Verwendung in virtuellen Desktopumgebungen optimiert sind, können Sie diese Richtlinien wiederherstellen und Benutzern die Verwendung von Teams ermöglichen, wie dies normalerweise der Fall wäre.</span><span class="sxs-lookup"><span data-stu-id="74d41-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="74d41-119">Anrufe</span><span class="sxs-lookup"><span data-stu-id="74d41-119">Calling</span></span>

<span data-ttu-id="74d41-120">Verwenden Sie die **CSTeamsCallingPolicy** -Cmdlets, um zu steuern, ob Benutzer in privaten und Gruppen-Chats Anruf-und Anrufoptionen verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="74d41-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="74d41-121">Hier sehen Sie die Liste der Richtlinieneinstellungen und empfohlenen Werte.</span><span class="sxs-lookup"><span data-stu-id="74d41-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="74d41-122">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="74d41-122">Policy name</span></span>  |<span data-ttu-id="74d41-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74d41-123">Description</span></span> |<span data-ttu-id="74d41-124">Empfohlener Wert</span><span class="sxs-lookup"><span data-stu-id="74d41-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="74d41-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="74d41-125">AllowCalling</span></span>    |<span data-ttu-id="74d41-126">Steuert die Interop-Aufruf Funktionen.</span><span class="sxs-lookup"><span data-stu-id="74d41-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="74d41-127">Wenn Sie diese Option aktivieren, können Skype for Business-Benutzern Einzelgespräche mit Teams und umgekehrt führen.</span><span class="sxs-lookup"><span data-stu-id="74d41-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="74d41-128">Auf "false" festlegen, um zu verhindern, dass Anrufe von Skype for Business-Benutzern in Teams anlanden.</span><span class="sxs-lookup"><span data-stu-id="74d41-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="74d41-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="74d41-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="74d41-130">Steuert, ob die aufrufende app in der APP-Leiste auf der linken Seite des Teams-Clients verfügbar ist und ob Benutzer im privaten Chat Anruf-und Video Anrufoptionen sehen</span><span class="sxs-lookup"><span data-stu-id="74d41-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="74d41-131">Auf "false" festlegen, um die Anruf-App aus der APP-Leiste auf der linken Seite von Teams zu entfernen und die Anruf-und Video Anrufoptionen im privaten Chat zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="74d41-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="74d41-132">Erstellen und Zuweisen einer Anrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="74d41-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="74d41-133">Starten Sie eine Windows PowerShell-Sitzung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="74d41-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="74d41-134">Stellen Sie eine Verbindung mit dem Skype Online-Connector her.</span><span class="sxs-lookup"><span data-stu-id="74d41-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="74d41-135">Anzeigen einer Liste der Anruf Richtlinienoptionen</span><span class="sxs-lookup"><span data-stu-id="74d41-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="74d41-136">Suchen Sie nach der integrierten Richtlinienoption, bei der alle Anruf Richtlinien deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="74d41-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="74d41-137">Es sieht so aus.</span><span class="sxs-lookup"><span data-stu-id="74d41-137">It looks like this.</span></span>
   
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

5. <span data-ttu-id="74d41-138">Wenden Sie die integrierte Richtlinienoption DisallowCalling auf alle Benutzer an, die Teams in einer virtualisierten Umgebung verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="74d41-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="74d41-139">Weitere Informationen zu den Anruf Richtlinien für Teams finden Sie unter [Satz-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="74d41-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="74d41-140">Besprechungen</span><span class="sxs-lookup"><span data-stu-id="74d41-140">Meetings</span></span>

<span data-ttu-id="74d41-141">Verwenden Sie die **CsTeamsMeetingPolicy** -Cmdlets, um die Art der Besprechungen zu steuern, die Benutzer erstellen können, die Features, auf die Sie während einer Besprechung zugreifen können, und die besprechungsfeatures, die anonymen und externen Benutzern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="74d41-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="74d41-142">Hier sehen Sie die Liste der Richtlinieneinstellungen und empfohlenen Werte.</span><span class="sxs-lookup"><span data-stu-id="74d41-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="74d41-143">Richtlinien Name</span><span class="sxs-lookup"><span data-stu-id="74d41-143">Policy Name</span></span> |<span data-ttu-id="74d41-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74d41-144">Description</span></span>|<span data-ttu-id="74d41-145">Empfohlener Wert</span><span class="sxs-lookup"><span data-stu-id="74d41-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="74d41-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="74d41-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="74d41-147">Bestimmt, ob ein Benutzer private Besprechungen planen darf.</span><span class="sxs-lookup"><span data-stu-id="74d41-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="74d41-148">Auf "false" festlegen, um zu verhindern, dass der Benutzer private Besprechungen planen kann.</span><span class="sxs-lookup"><span data-stu-id="74d41-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="74d41-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="74d41-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="74d41-150">Bestimmt, ob ein Benutzerkanal Besprechungen planen darf.</span><span class="sxs-lookup"><span data-stu-id="74d41-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="74d41-151">Auf "false" festlegen, um zu verhindern, dass der Benutzerkanal Besprechungen planen kann.</span><span class="sxs-lookup"><span data-stu-id="74d41-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="74d41-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="74d41-152">AllowMeetNow</span></span> |<span data-ttu-id="74d41-153">Bestimmt, ob ein Benutzer die Möglichkeit hat, Ad-hoc-Besprechungen zu erstellen oder zu starten.</span><span class="sxs-lookup"><span data-stu-id="74d41-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="74d41-154">Legen Sie diesen Wert auf "false" fest, um zu verhindern, dass der Benutzer Ad-hoc-Besprechungen starten kann.</span><span class="sxs-lookup"><span data-stu-id="74d41-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="74d41-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="74d41-155">ScreenSharingMode</span></span> | <span data-ttu-id="74d41-156">Bestimmt den Modus, in dem ein Benutzer seinen Bildschirm in anrufen oder Besprechungen freigeben darf.</span><span class="sxs-lookup"><span data-stu-id="74d41-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="74d41-157">Auf "deaktiviert" setzen, um zu verhindern, dass Benutzer ihre Bildschirme freigeben</span><span class="sxs-lookup"><span data-stu-id="74d41-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="74d41-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="74d41-158">AllowIPVideo</span></span> |<span data-ttu-id="74d41-159">Bestimmt, ob Video in den Besprechungen oder Anrufen eines Benutzers aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="74d41-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="74d41-160">Auf "false" festlegen, um zu verhindern, dass der Benutzer sein Video freigibt</span><span class="sxs-lookup"><span data-stu-id="74d41-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="74d41-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="74d41-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="74d41-162">Bestimmt, ob anonyme Benutzer die Möglichkeit haben, sich an eine PSTN-Nummer zu wählen.</span><span class="sxs-lookup"><span data-stu-id="74d41-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="74d41-163">Auf "false" festlegen, um zu verhindern, dass anonyme Benutzer sich auswählen</span><span class="sxs-lookup"><span data-stu-id="74d41-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="74d41-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="74d41-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="74d41-165">Bestimmt, ob anonyme Benutzer eine Besprechung starten können.</span><span class="sxs-lookup"><span data-stu-id="74d41-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="74d41-166">Auf "false" festlegen, um zu verhindern, dass Benutzer eine Besprechung starten</span><span class="sxs-lookup"><span data-stu-id="74d41-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="74d41-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="74d41-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="74d41-168">Bestimmt, ob ein Benutzer Teambesprechungen im Outlook-Desktop Client planen kann.</span><span class="sxs-lookup"><span data-stu-id="74d41-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="74d41-169">Auf "false" festlegen, um einem Benutzer das Planen von Teams-Besprechungen im Outlook-Desktop Client zu verbieten</span><span class="sxs-lookup"><span data-stu-id="74d41-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="74d41-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="74d41-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="74d41-171">Bestimmt, ob Teilnehmer die Bildschirmfreigabe anfordern oder kontrollieren können.</span><span class="sxs-lookup"><span data-stu-id="74d41-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="74d41-172">Auf "false" festlegen, um zu verhindern, dass der Benutzer die Steuerung in einer Besprechung erteilt und anfordert</span><span class="sxs-lookup"><span data-stu-id="74d41-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="74d41-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="74d41-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="74d41-174">Bestimmt, ob externe Teilnehmer die Bildschirmfreigabe anfordern oder kontrollieren können.</span><span class="sxs-lookup"><span data-stu-id="74d41-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="74d41-175">Auf "false" festlegen, um zu verhindern, dass ein externer Benutzer die Steuerung in einer Besprechung anfordert</span><span class="sxs-lookup"><span data-stu-id="74d41-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="74d41-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="74d41-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="74d41-177">Bestimmt, ob PowerPoint-Freigabe in den Besprechungen eines Benutzers zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="74d41-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="74d41-178">Auf "false" festlegen, um einen Benutzer zu verbieten, PowerPoint-Dateien in einer Besprechung freizugeben</span><span class="sxs-lookup"><span data-stu-id="74d41-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="74d41-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="74d41-179">AllowWhiteboard</span></span> | <span data-ttu-id="74d41-180">Bestimmt, ob Whiteboard in den Besprechungen eines Benutzers zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="74d41-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="74d41-181">Auf "false" festlegen, um das Whiteboard in einer Besprechung zu verbieten</span><span class="sxs-lookup"><span data-stu-id="74d41-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="74d41-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="74d41-182">AllowTranscription</span></span> |<span data-ttu-id="74d41-183">Bestimmt, ob in den Besprechungen eines Benutzers Echt Zeit-und/oder Post-Meeting-Beschriftungen und-Transkriptionen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="74d41-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="74d41-184">Auf "false" festlegen, um Transkription und Beschriftungen in einer Besprechung zu untersagen</span><span class="sxs-lookup"><span data-stu-id="74d41-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="74d41-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="74d41-185">AllowSharedNotes</span></span> | <span data-ttu-id="74d41-186">Bestimmt, ob Benutzer freigegebene Notizen übernehmen dürfen.</span><span class="sxs-lookup"><span data-stu-id="74d41-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="74d41-187">Auf "false" festlegen, um zu verhindern, dass Benutzer freigegebene Notizen erstellen</span><span class="sxs-lookup"><span data-stu-id="74d41-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="74d41-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="74d41-188">MediaBitRateKB</span></span> |<span data-ttu-id="74d41-189">Bestimmt die Medien Bitrate für Audio/Video/App-Freigabe Übertragungen in Besprechungen</span><span class="sxs-lookup"><span data-stu-id="74d41-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="74d41-190">Der vorgeschlagene Wert ist 5000 (5 MB).</span><span class="sxs-lookup"><span data-stu-id="74d41-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="74d41-191">Sie können es entsprechend den Anforderungen Ihrer Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="74d41-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="74d41-192">Erstellen und Zuweisen einer Besprechungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="74d41-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="74d41-193">Starten Sie eine Windows PowerShell-Sitzung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="74d41-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="74d41-194">Stellen Sie eine Verbindung mit dem Skype Online-Connector her.</span><span class="sxs-lookup"><span data-stu-id="74d41-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="74d41-195">Anzeigen einer Liste der Besprechungsrichtlinien Optionen</span><span class="sxs-lookup"><span data-stu-id="74d41-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="74d41-196">Suchen Sie nach der integrierten Richtlinienoption, bei der alle Besprechungsrichtlinien deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="74d41-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="74d41-197">Es sieht so aus.</span><span class="sxs-lookup"><span data-stu-id="74d41-197">It looks like this.</span></span>
   
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
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="74d41-198">Wenden Sie die integrierte Richtlinienoption AllOff auf alle Benutzer an, die Teams in einer virtualisierten Umgebung verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="74d41-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="74d41-199">Weitere Informationen zu den Team-Besprechungsrichtlinien finden Sie unter [Satz-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="74d41-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="74d41-200">Anforderungen des Virtualisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="74d41-200">Virtualization provider requirements</span></span>

<span data-ttu-id="74d41-201">Die Teams-App wurde bei führenden Anbietern von Virtualisierungslösungen validiert.</span><span class="sxs-lookup"><span data-stu-id="74d41-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="74d41-202">Bei mehreren Marktanbietern wenden Sie sich an Ihren Anbieter von Virtualisierungslösungen, um sicherzustellen, dass die Mindestanforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="74d41-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="74d41-203">Anforderungen virtueller Computer</span><span class="sxs-lookup"><span data-stu-id="74d41-203">Virtual Machine requirements</span></span>

<span data-ttu-id="74d41-204">Mit den unterschiedlichen Arbeitslasten und Benutzeranforderungen in einer virtualisierten Umgebung ist die folgende Mindestkonfiguration für VM empfohlen.</span><span class="sxs-lookup"><span data-stu-id="74d41-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="74d41-205">Parameter</span><span class="sxs-lookup"><span data-stu-id="74d41-205">Parameter</span></span>  |<span data-ttu-id="74d41-206">Maßnahme</span><span class="sxs-lookup"><span data-stu-id="74d41-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="74d41-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="74d41-207">vCPU</span></span>    |  <span data-ttu-id="74d41-208">2 Kerne</span><span class="sxs-lookup"><span data-stu-id="74d41-208">2 cores</span></span>       |
|<span data-ttu-id="74d41-209">RAM</span><span class="sxs-lookup"><span data-stu-id="74d41-209">RAM</span></span>     |  <span data-ttu-id="74d41-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="74d41-210">4 GB</span></span>      |
|<span data-ttu-id="74d41-211">Speicher</span><span class="sxs-lookup"><span data-stu-id="74d41-211">Storage</span></span>     | <span data-ttu-id="74d41-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="74d41-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="74d41-213">Betriebssystemanforderungen für virtuelle Maschinen</span><span class="sxs-lookup"><span data-stu-id="74d41-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="74d41-214">Die unterstützten Betriebssysteme für VM sind:</span><span class="sxs-lookup"><span data-stu-id="74d41-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="74d41-215">Windows 10 und höher</span><span class="sxs-lookup"><span data-stu-id="74d41-215">Windows 10 and later</span></span>
- <span data-ttu-id="74d41-216">Windows Server 2012 R2 und höher</span><span class="sxs-lookup"><span data-stu-id="74d41-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="74d41-217">Installieren von Teams auf VDI</span><span class="sxs-lookup"><span data-stu-id="74d41-217">Install Teams on VDI</span></span>

<span data-ttu-id="74d41-218">Hier sehen Sie den Prozess und die Tools zum Bereitstellen der Desktop-App von Teams.</span><span class="sxs-lookup"><span data-stu-id="74d41-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="74d41-219">Laden Sie das MSI-Paket für Teams mit einem der folgenden Links in Abhängigkeit von der Umgebung herunter.</span><span class="sxs-lookup"><span data-stu-id="74d41-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="74d41-220">Wir empfehlen die 64-Bit-Version für eine VDI-VM mit einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="74d41-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="74d41-221">32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="74d41-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="74d41-222">64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="74d41-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="74d41-223">Führen Sie den folgenden Befehl aus, um die MSI-Datei auf der VDI-VM zu installieren (oder vollständig zu aktualisieren).</span><span class="sxs-lookup"><span data-stu-id="74d41-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="74d41-224">Dadurch werden Teams in Programmdateien installiert.</span><span class="sxs-lookup"><span data-stu-id="74d41-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="74d41-225">An diesem Punkt ist die Einrichtung des goldenen Bilds abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="74d41-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="74d41-226">In der nächsten interaktiven Anmeldesitzung werden Teams gestartet, und es werden Anmeldeinformationen angefordert.</span><span class="sxs-lookup"><span data-stu-id="74d41-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="74d41-227">Beachten Sie, dass es nicht möglich ist, den automatischen Start von Teams bei der Installation von Teams auf VDI mithilfe der alluser-Eigenschaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="74d41-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="74d41-228">Führen Sie den folgenden Befehl aus, um die MSI-Datei von der VDI-VM zu deinstallieren (oder die Aktualisierung vorzubereiten).</span><span class="sxs-lookup"><span data-stu-id="74d41-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="74d41-229">Dadurch wird Microsoft Teams aus Programmdateien deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="74d41-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="74d41-230">Bekannte Probleme und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="74d41-230">Known issues and limitations</span></span>

<span data-ttu-id="74d41-231">Im folgenden sind bekannte Probleme und Einschränkungen für Teams in VDI zu finden.</span><span class="sxs-lookup"><span data-stu-id="74d41-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="74d41-232">**Bereitstellungen für Shared Session**-Hosttypen: Bereitstellungen für Shared Session-Hosttypen (beispielsweise freigegebene nicht persistente VM-Konfiguration) sind nicht im Bereich.</span><span class="sxs-lookup"><span data-stu-id="74d41-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="74d41-233">**Anrufe und Besprechungen**:</span><span class="sxs-lookup"><span data-stu-id="74d41-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="74d41-234">Anruf-und Besprechungs Szenarien sind für VDI nicht optimiert.</span><span class="sxs-lookup"><span data-stu-id="74d41-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="74d41-235">Diese Szenarien werden schlecht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="74d41-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="74d41-236">Wir empfehlen die Verwendung von Richtlinien auf Benutzerebene, wie im Abschnitt [Richtlinien zum Deaktivieren von Anrufen und Besprechungsfunktionen in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74d41-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="74d41-237">Die Anwendung der in diesem Artikel beschriebenen Richtlinien wirkt sich auf die Möglichkeit aus, die Funktionalität von Anrufen und Besprechungen zu verwenden, die sich je nach anderen Richtlinien auf andere Benutzer in Ihrer Organisation auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="74d41-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="74d41-238">Wenn Benutzer in Ihrer Organisation nicht-VDI-Clients verwenden, können Sie festlegen, dass die Richtlinien nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="74d41-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="74d41-239">**Teilnahme an anrufen und Besprechungen, die von anderen Benutzern erstellt wurden**: Obwohl die Richtlinien Benutzer daran hindern, Besprechungen zu erstellen, können Sie weiterhin an Besprechungen teilnehmen, wenn sich ein anderer Benutzer aus der Besprechung anwählt.</span><span class="sxs-lookup"><span data-stu-id="74d41-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="74d41-240">In diesen Besprechungen hängt die Möglichkeit des Benutzers, Video zu teilen, die Verwendung von Whiteboard und anderen Features davon ab, ob Sie diese Features mithilfe von TeamsMeetingPolicy deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="74d41-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="74d41-241">**Zwischengespeicherter Inhalt**: Wenn die virtuelle Umgebung, in der die Teams ausgeführt werden, nicht persistent ist (und die Daten am Ende jeder Benutzersitzung bereinigt werden), können Benutzer die Leistungsverschlechterung aufgrund der Inhaltsaktualisierung bemerken, unabhängig davon, ob der Benutzer auf dieselbe Inhalt in einer vorherigen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="74d41-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="74d41-242">**Client Updates**: Teams auf VDI werden nicht automatisch aktualisiert, wie dies bei Clients außerhalb der VDI-Teams der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="74d41-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="74d41-243">Sie müssen das VM-Abbild aktualisieren, indem Sie eine neue MSI-Datei installieren, wie im Abschnitt [Installieren von Teams im VDI](#install-teams-on-vdi) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74d41-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="74d41-244">Sie müssen die aktuelle Version deinstallieren, um Sie auf eine neuere Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="74d41-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="74d41-245">**Benutzererfahrung**: die Benutzeroberfläche von Teams in einer VDI-Umgebung kann sich von einer nicht-VDI-Umgebung unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="74d41-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="74d41-246">Die Unterschiede sind möglicherweise auf Richtlinieneinstellungen und/oder Funktionsunterstützung in der Umgebung zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="74d41-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="74d41-247">Informationen zu bekannten Problemen, die nicht mit VDI in Verbindung stehen, finden Sie unter [bekannte Probleme für Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="74d41-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="74d41-248">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="74d41-248">Related topics</span></span>

- [<span data-ttu-id="74d41-249">Installieren von Microsoft Teams mithilfe eines MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="74d41-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
