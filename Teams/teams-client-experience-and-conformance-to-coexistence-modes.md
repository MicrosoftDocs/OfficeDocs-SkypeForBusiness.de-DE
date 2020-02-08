---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 94126a5d49c9573751279c645024dcb9d164bd90
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863296"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="0aa00-103">Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen</span><span class="sxs-lookup"><span data-stu-id="0aa00-103">Teams client experience and conformance to coexistence modes</span></span>


<span data-ttu-id="0aa00-104">Der Zweck der Koexistenz-Modi von Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht darin, den Endbenutzern eine einfache, vorhersagbare Erfahrung zu bieten, wenn Organisationen von Skype for Business zu Teams wechseln.</span><span class="sxs-lookup"><span data-stu-id="0aa00-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="0aa00-105">Für eine Organisation, die in Teams wechselt, ist der Modus **nur für Teams** das endgültige Ziel für jeden Benutzer, wobei nicht allen Benutzern gleichzeitig **nur Teams** (oder ein beliebiger anderer Modus) zugewiesen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0aa00-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="0aa00-106">Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen alle Skype for Business-Koexistenzmodus verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern zu gewährleisten, die **nur Teams** sind und die noch nicht sind.</span><span class="sxs-lookup"><span data-stu-id="0aa00-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren’t yet.</span></span> 

<span data-ttu-id="0aa00-107">Wenn sich ein Nutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0aa00-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="0aa00-108">Um die Verwirrung des Endbenutzers zu vermeiden und die ordnungsgemäße Weiterleitung zu gewährleisten, ist die Funktion für Anrufe und Chats im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet.</span><span class="sxs-lookup"><span data-stu-id="0aa00-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="0aa00-109">Ebenso wird die Terminplanung in Teams explizit deaktiviert, wenn sich Benutzer im SfBOnly-oder SfBWithTeamsCollab-Modus befinden und explizit aktiviert werden, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="0aa00-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="0aa00-110">Da Anwesenheitsinformationen durch Chats und Anrufe eine Erreichbarkeit darstellen, wenn Chats und Anrufe deaktiviert sind, ist die selbst Anwesenheit in Teams (also die Anzeige der eigenen Anwesenheit im Team-Client im Bild des Benutzers) ebenfalls verborgen.</span><span class="sxs-lookup"><span data-stu-id="0aa00-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one’s own presence in the Teams client in the user’s picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="0aa00-111">Wie sich die verfügbaren Funktionen in Teams Client basierend auf dem Modus ändern</span><span class="sxs-lookup"><span data-stu-id="0aa00-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="0aa00-112">Die verfügbare Funktionalität in Microsoft Teams hängt vom Koexistenzmodus des Benutzers ab, wie von TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="0aa00-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="0aa00-113">In der folgenden Tabelle wird das Verhalten zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="0aa00-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="0aa00-114">Effektiver Modus des Benutzers</span><span class="sxs-lookup"><span data-stu-id="0aa00-114">User's effective mode</span></span>|<span data-ttu-id="0aa00-115">Erfahrung im Team-Client</span><span class="sxs-lookup"><span data-stu-id="0aa00-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="0aa00-116">Skype for Business-Modus</span><span class="sxs-lookup"><span data-stu-id="0aa00-116">Any Skype for Business mode</span></span>|<span data-ttu-id="0aa00-117">Anrufe, Chats und selbst Anwesenheit sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0aa00-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="0aa00-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="0aa00-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="0aa00-119">Besprechungsplanung steht zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="0aa00-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="0aa00-120">SfBWithTeamsCollab oder SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0aa00-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="0aa00-121">Besprechungsplanung steht nicht zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="0aa00-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="0aa00-122">Die folgenden Screenshots veranschaulichen den Unterschied zwischen dem **nur für Teams** oder dem **Inseln** -Modus und allen anderen Modi.</span><span class="sxs-lookup"><span data-stu-id="0aa00-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="0aa00-123">Beachten Sie, dass die Symbole für Chats und Anrufe standardmäßig im Modus " **nur für Teams** " oder " **Inseln** " verfügbar sind (Screenshot Links), aber nicht mit den anderen Modi (rechter Screenshot):</span><span class="sxs-lookup"><span data-stu-id="0aa00-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Ein nebeneinander angeordneter Vergleich der Modi "Teams"](media/teams-mode-comparison.png)

<span data-ttu-id="0aa00-125">Darüber hinaus steht die selbst Anwesenheit in den anderen Modi nicht zur Verfügung, wie hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0aa00-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Screenshot der selbst Anwesenheit in Besprechungen zuerst](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="0aa00-127">**Hinweis:**
<sup>1</sup> zu diesem Zeitpunkt Verhalten sich SfBwithTeamsCollab und SfBOnly identisch, aber die Absicht ist, dass der SfBOnly-Modus auch Kanäle und Dateien in Teams deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0aa00-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="0aa00-128">In der Zwischenzeit können Kanäle mithilfe der APP-Berechtigungsrichtlinie ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="0aa00-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="0aa00-129">Auswirkungen des Modus auf andere Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="0aa00-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="0aa00-130">Wie oben beschrieben, hat der Koexistenzmodus des Benutzers Auswirkungen auf die Funktionalität, die im Team Client des Benutzers zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="0aa00-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="0aa00-131">Dies bedeutet, dass der Wert von Mode je nach Modus Vorrang vor dem Wert anderer Richtlinieneinstellungen haben kann.</span><span class="sxs-lookup"><span data-stu-id="0aa00-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="0aa00-132">Insbesondere beeinflusst der Koexistenzmodus, ob die folgenden Richtlinieneinstellungen beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="0aa00-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="0aa00-133">**Modalität (app)**</span><span class="sxs-lookup"><span data-stu-id="0aa00-133">**Modality (App)**</span></span>|<span data-ttu-id="0aa00-134">**Richtlinie. Setting**</span><span class="sxs-lookup"><span data-stu-id="0aa00-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="0aa00-135">Chat</span><span class="sxs-lookup"><span data-stu-id="0aa00-135">Chat</span></span>|<span data-ttu-id="0aa00-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="0aa00-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="0aa00-137">Anrufe</span><span class="sxs-lookup"><span data-stu-id="0aa00-137">Calling</span></span>|<span data-ttu-id="0aa00-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="0aa00-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="0aa00-139">Besprechungsplanung</span><span class="sxs-lookup"><span data-stu-id="0aa00-139">Meeting scheduling</span></span>|<span data-ttu-id="0aa00-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0aa00-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="0aa00-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0aa00-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="0aa00-142">Administratoren müssen diese Richtlinieneinstellungen *nicht* explizit festlegen, wenn Sie den Koexistenzmodus verwenden, doch es ist wichtig zu wissen, dass sich diese Einstellungen für einen bestimmten Modus wie folgt Verhalten.</span><span class="sxs-lookup"><span data-stu-id="0aa00-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="0aa00-143">Modus</span><span class="sxs-lookup"><span data-stu-id="0aa00-143">Mode</span></span>|<span data-ttu-id="0aa00-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="0aa00-144">AllowUserChat</span></span>|<span data-ttu-id="0aa00-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="0aa00-145">AllowPrivateCalling</span></span>|<span data-ttu-id="0aa00-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0aa00-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="0aa00-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0aa00-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="0aa00-148">TeamsOnly oder-Inseln</span><span class="sxs-lookup"><span data-stu-id="0aa00-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="0aa00-149">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-149">Enabled</span></span>|<span data-ttu-id="0aa00-150">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-150">Enabled</span></span>|<span data-ttu-id="0aa00-151">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-151">Enabled</span></span>|<span data-ttu-id="0aa00-152">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-152">Enabled</span></span>|
|<span data-ttu-id="0aa00-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="0aa00-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="0aa00-154">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-154">Disabled</span></span>|<span data-ttu-id="0aa00-155">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-155">Disabled</span></span>|<span data-ttu-id="0aa00-156">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-156">Enabled</span></span>|<span data-ttu-id="0aa00-157">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-157">Enabled</span></span>|
|<span data-ttu-id="0aa00-158">SfBWithTeamsCollab oder SfBOnly</span><span class="sxs-lookup"><span data-stu-id="0aa00-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="0aa00-159">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-159">Disabled</span></span>|<span data-ttu-id="0aa00-160">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-160">Disabled</span></span>|<span data-ttu-id="0aa00-161">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-161">Disabled</span></span>|<span data-ttu-id="0aa00-162">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="0aa00-162">Disabled</span></span>|
||||||

<span data-ttu-id="0aa00-163">Bei Verwendung von PowerShell überprüft `Grant-CsTeamsUpgradePolicy` das Cmdlet die Konfiguration der entsprechenden Einstellungen in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, um festzustellen, ob diese Einstellungen durch TeamsUpgradePolicy ersetzt würden, und wenn dies der Fall ist, wird in PowerShell eine Informationsmeldung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0aa00-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="0aa00-164">Wie bereits erwähnt, ist es nicht mehr notwendig, diese anderen Richtlinieneinstellungen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0aa00-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="0aa00-165">Im folgenden sehen Sie ein Beispiel dafür, wie die PowerShell-Warnung aussieht:</span><span class="sxs-lookup"><span data-stu-id="0aa00-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="0aa00-166">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0aa00-166">Related topics</span></span>

[<span data-ttu-id="0aa00-167">Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="0aa00-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




