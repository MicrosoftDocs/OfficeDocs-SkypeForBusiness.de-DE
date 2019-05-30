---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Clientumgebung für Teams und comformance in Koexistenzmodus
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548653"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="f88be-103">Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen</span><span class="sxs-lookup"><span data-stu-id="f88be-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="f88be-104">Auf dieser Seite werden wichtige, kürzlich veröffentlichte Änderungen des Verhaltens des Teams-Clients beschrieben, wenn sich Benutzer in einem der Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) befinden.</span><span class="sxs-lookup"><span data-stu-id="f88be-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="f88be-105">Der Zweck der Koexistenz-Modi ist es, eine einfache, vorhersagbare Benutzeroberfläche für Endbenutzer bereitzustellen, während Organisationen von Skype for Business zu Teams wechseln.</span><span class="sxs-lookup"><span data-stu-id="f88be-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="f88be-106">Für eine Organisation, die in Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer, wobei nicht allen Benutzern gleichzeitig TeamsOnly (oder ein beliebiger anderer Modus) zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="f88be-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="f88be-107">Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen alle Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern, die TeamsOnly sind, und denjenigen, die noch nicht sind, zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="f88be-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="f88be-108">Wenn sich ein Nutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="f88be-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="f88be-109">Um die Verwirrung des Endbenutzers zu vermeiden und die ordnungsgemäße Weiterleitung zu gewährleisten, ist die Funktion für Anrufe und Chats im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet.</span><span class="sxs-lookup"><span data-stu-id="f88be-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="f88be-110">Ebenso wird die Terminplanung in Teams explizit deaktiviert, wenn sich Benutzer im SfBOnly-oder SfBWithTeamsCollab-Modus befinden und explizit aktiviert werden, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="f88be-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="f88be-111">Wie sich die verfügbaren Funktionen in Teams Client basierend auf dem Modus ändern</span><span class="sxs-lookup"><span data-stu-id="f88be-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="f88be-112">Die verfügbare Funktionalität in Microsoft Teams hängt vom Koexistenzmodus des Benutzers ab, wie von TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="f88be-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="f88be-113">In der folgenden Tabelle wird das Verhalten zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="f88be-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="f88be-114">Effektiver Modus des Benutzers</span><span class="sxs-lookup"><span data-stu-id="f88be-114">User's effective mode</span></span>|<span data-ttu-id="f88be-115">Erfahrung im Team-Client</span><span class="sxs-lookup"><span data-stu-id="f88be-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="f88be-116">Skype for Business-Modus</span><span class="sxs-lookup"><span data-stu-id="f88be-116">Any Skype for Business mode</span></span>|<span data-ttu-id="f88be-117">Anrufe und Chats sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f88be-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="f88be-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="f88be-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="f88be-119">Besprechungsplanung steht zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="f88be-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="f88be-120">SfBWithTeamsCollab oder SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f88be-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="f88be-121">Besprechungsplanung steht nicht zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="f88be-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="f88be-122">Die folgenden Screenshots veranschaulichen den Unterschied zwischen TeamsOnly-oder Islands-Modus und allen anderen Modi.</span><span class="sxs-lookup"><span data-stu-id="f88be-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="f88be-123">Beachten Sie, dass die Chat-und Anruf Symbole im TeamsOnly-oder Islands-Modus (linker Screenshot) zur Verfügung stehen, aber nicht bei den anderen Modi (rechter Screenshot):</span><span class="sxs-lookup"><span data-stu-id="f88be-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Ein nebeneinander angeordneter Vergleich der Modi "Teams"](media/teams-mode-comparison.png)


 
<span data-ttu-id="f88be-125">**Hinweis:**
<sup>1</sup> im Moment Verhalten sich SfBwithTeamsCollab und SfBOnly identisch, aber die Absicht ist, dass der SfBOnly-Modus auch die Kanäle und Dateien in Teams deaktiviert. Es gibt jedoch derzeit keine Einstellung, mit der diese Funktion in Teams deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f88be-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="f88be-126">Auswirkungen des Modus auf andere Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="f88be-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="f88be-127">Wie oben beschrieben, hat der Koexistenzmodus des Benutzers Auswirkungen auf die Funktionalität, die im Team Client des Benutzers zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="f88be-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="f88be-128">Dies bedeutet, dass der Wert von Mode je nach Modus Vorrang vor dem Wert anderer Richtlinieneinstellungen haben kann.</span><span class="sxs-lookup"><span data-stu-id="f88be-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="f88be-129">Insbesondere beeinflusst der Koexistenzmodus, ob die folgenden Richtlinieneinstellungen beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="f88be-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="f88be-130">**Modalität (app)**</span><span class="sxs-lookup"><span data-stu-id="f88be-130">**Modality (App)**</span></span>|<span data-ttu-id="f88be-131">**Richtlinie. Setting**</span><span class="sxs-lookup"><span data-stu-id="f88be-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="f88be-132">Chat</span><span class="sxs-lookup"><span data-stu-id="f88be-132">Chat</span></span>|<span data-ttu-id="f88be-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="f88be-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="f88be-134">Anrufe</span><span class="sxs-lookup"><span data-stu-id="f88be-134">Calling</span></span>|<span data-ttu-id="f88be-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="f88be-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="f88be-136">Besprechungsplanung</span><span class="sxs-lookup"><span data-stu-id="f88be-136">Meeting scheduling</span></span>|<span data-ttu-id="f88be-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f88be-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="f88be-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f88be-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="f88be-139">Administratoren müssen diese Richtlinieneinstellungen *nicht* explizit festlegen, wenn Sie den Koexistenzmodus verwenden, doch es ist wichtig zu wissen, dass sich diese Einstellungen für einen bestimmten Modus wie folgt Verhalten.</span><span class="sxs-lookup"><span data-stu-id="f88be-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="f88be-140">Modus</span><span class="sxs-lookup"><span data-stu-id="f88be-140">Mode</span></span>|<span data-ttu-id="f88be-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="f88be-141">AllowUserChat</span></span>|<span data-ttu-id="f88be-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="f88be-142">AllowPrivateCalling</span></span>|<span data-ttu-id="f88be-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f88be-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="f88be-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f88be-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="f88be-145">TeamsOnly oder-Inseln</span><span class="sxs-lookup"><span data-stu-id="f88be-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="f88be-146">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-146">Enabled</span></span>|<span data-ttu-id="f88be-147">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-147">Enabled</span></span>|<span data-ttu-id="f88be-148">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-148">Enabled</span></span>|<span data-ttu-id="f88be-149">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-149">Enabled</span></span>|
|<span data-ttu-id="f88be-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="f88be-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="f88be-151">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-151">Disabled</span></span>|<span data-ttu-id="f88be-152">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-152">Disabled</span></span>|<span data-ttu-id="f88be-153">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-153">Enabled</span></span>|<span data-ttu-id="f88be-154">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-154">Enabled</span></span>|
|<span data-ttu-id="f88be-155">SfBWithTeamsCollab oder SfBOnly</span><span class="sxs-lookup"><span data-stu-id="f88be-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="f88be-156">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-156">Disabled</span></span>|<span data-ttu-id="f88be-157">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-157">Disabled</span></span>|<span data-ttu-id="f88be-158">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-158">Disabled</span></span>|<span data-ttu-id="f88be-159">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f88be-159">Disabled</span></span>|
||||||

<span data-ttu-id="f88be-160">Bei Verwendung von PowerShell überprüft `Grant-CsTeamsUpgradePolicy` das Cmdlet die Konfiguration der entsprechenden Einstellungen in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, um festzustellen, ob diese Einstellungen von TeamsUpgradePolicy übergegangen werden, und wenn dies der Fall ist, wird eine eine Informationsmeldung wird in PowerShell bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f88be-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="f88be-161">Wie bereits erwähnt, ist es nicht mehr notwendig, diese anderen Richtlinieneinstellungen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f88be-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="f88be-162">Nachfolgend finden Sie ein Beispiel dafür, wie die PowerShell-Warnung aussieht:</span><span class="sxs-lookup"><span data-stu-id="f88be-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="f88be-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f88be-163">Related topics</span></span>

[<span data-ttu-id="f88be-164">Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="f88be-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




