---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Clientumgebung Teams und ASP.NET-Features, Koexistenz Modi
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 363da62c378a60cb85a9544339dbf7ccd699b7c0
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517079"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="59f71-103">Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen</span><span class="sxs-lookup"><span data-stu-id="59f71-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="59f71-104">Auf dieser Seite werden wichtige, kürzlich veröffentlichte Änderungen in das Verhalten des Teams-Clients beschrieben, wenn Benutzer in einer der der Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) sind.</span><span class="sxs-lookup"><span data-stu-id="59f71-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="59f71-105">Der Zweck der Koexistenz Modi darin eine einfache und vorhersehbare Erfahrung für Endbenutzer als Organisationen Übergang von Skype für Business Teams bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="59f71-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="59f71-106">Für eine Organisation verschieben, Teams ist der TeamsOnly-Modus der endgültigen Ziel für jeden Benutzer, wenn nicht alle Benutzer sich TeamsOnly (oder einem anderen Modus) zugewiesen werden zur gleichen Zeit müssen.</span><span class="sxs-lookup"><span data-stu-id="59f71-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="59f71-107">Vor dem Benutzer TeamsOnly Modus erreichen können Organisationen verwenden die Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), um sicherzustellen, dass vorhersehbare Kommunikation zwischen Benutzern, die TeamsOnly sind und Personen, die noch nicht.</span><span class="sxs-lookup"><span data-stu-id="59f71-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="59f71-108">Wenn ein Benutzer in einer der der Skype für Business Modi ist, werden alle eingehenden Chats und Anrufe an Skype für Business-Client des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="59f71-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="59f71-109">Endbenutzer Verwechslungen und die Sicherstellung ordnungsgemäßes routing, ist Anruf- und Chat Funktionalität in der Teams-Client deaktiviert, wenn ein Benutzer in einer der der Skype für Business Modi ist.</span><span class="sxs-lookup"><span data-stu-id="59f71-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="59f71-110">In ähnlicher Weise ist Besprechung planen in Teams explizit deaktiviert, wenn Benutzer in den SfBOnly oder SfBWithTeamsCollab Modi sind und explizit aktiviert, wenn ein Benutzer in den Modus SfBWithTeamsCollabAndMeetings ist.</span><span class="sxs-lookup"><span data-stu-id="59f71-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="59f71-111">Die verfügbare Funktionalität in Teams Client wie ändert basierend auf Modus</span><span class="sxs-lookup"><span data-stu-id="59f71-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="59f71-112">Die verfügbare Funktionalität in Teams hängt die Benutzermodus Koexistenz von TeamsUpgradePolicy festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="59f71-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="59f71-113">In der folgenden Tabelle wird das Verhalten zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="59f71-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="59f71-114">Eine effektive Benutzermodus</span><span class="sxs-lookup"><span data-stu-id="59f71-114">User's effective mode</span></span>|<span data-ttu-id="59f71-115">Erleben Sie die Teams-Client</span><span class="sxs-lookup"><span data-stu-id="59f71-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="59f71-116">Skype für Business-Modus</span><span class="sxs-lookup"><span data-stu-id="59f71-116">Any Skype for Business mode</span></span>|<span data-ttu-id="59f71-117">Anruf- und Chat<sup>1</sup> sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="59f71-117">Calling and Chat<sup>1</sup> are disabled.</span></span>|
|<span data-ttu-id="59f71-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="59f71-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="59f71-119">Besprechung planen, ist verfügbar</span><span class="sxs-lookup"><span data-stu-id="59f71-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="59f71-120">SfBWithTeamsCollab oder SfBOnly<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="59f71-120">SfBWithTeamsCollab or SfBOnly<sup>2</sup></span></span>|<span data-ttu-id="59f71-121">Besprechung planen ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="59f71-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="59f71-122">Die folgenden Screenshots sehen Sie den Unterschied zwischen TeamsOnly oder Inseln-Modus und alle anderen Modi.</span><span class="sxs-lookup"><span data-stu-id="59f71-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="59f71-123">Beachten Sie, dass die Symbole Chat und Aufrufen von TeamsOnly oder Inseln-Modus (links Screenshot), aber nicht mit den anderen Modi (rechts Screenshot) zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="59f71-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Zeigt Teams Modus Vergleiche](media/teams-mode-comparison.png)


 
<span data-ttu-id="59f71-125">**Hinweise:**
<sup>1</sup> Meeting Chat weiterhin verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="59f71-125">**Notes:**
<sup>1</sup> Meeting chat is still available.</span></span>

<span data-ttu-id="59f71-126"><sup>2</sup> für den Moment SfBwithTeamsCollab und SfBOnly Verhalten sich, aber die Absicht für SfBOnly Modus auch deaktivieren, Kanäle und Dateien Funktonalität Teams; Es ist derzeit keine Einstellung, die mit dieser Funktionalität in Teams deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="59f71-126"><sup>2</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="59f71-127">Auswirkung von Modus auf anderen Einstellungen für die Informationsverwaltungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="59f71-127">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="59f71-128">Wie oben, eines Benutzers Koexistenz Modus Auswirkungen beschrieben ist welche Funktionalität in der Client des Benutzers Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="59f71-128">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="59f71-129">Dies bedeutet, dass der Wert der Modus Vorrang gegenüber dem Wert der anderen Richtlinieneinstellungen, je nach den Modus haben kann.</span><span class="sxs-lookup"><span data-stu-id="59f71-129">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="59f71-130">Wirkt sich insbesondere auf Koexistenzmodus, ob die folgenden Richtlinieneinstellungen beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="59f71-130">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="59f71-131">**Modalität (App)**</span><span class="sxs-lookup"><span data-stu-id="59f71-131">**Modality (App)**</span></span>|<span data-ttu-id="59f71-132">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="59f71-132">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="59f71-133">Chat</span><span class="sxs-lookup"><span data-stu-id="59f71-133">Chat</span></span>|<span data-ttu-id="59f71-134">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="59f71-134">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="59f71-135">Anrufe</span><span class="sxs-lookup"><span data-stu-id="59f71-135">Calling</span></span>|<span data-ttu-id="59f71-136">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="59f71-136">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="59f71-137">Besprechung planen</span><span class="sxs-lookup"><span data-stu-id="59f71-137">Meeting scheduling</span></span>|<span data-ttu-id="59f71-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="59f71-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="59f71-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="59f71-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="59f71-140">Administratoren müssen *nicht* mit diesen Richtlinien explizit festlegen, wenn mit Koexistenz Modus, aber es wichtig ist zu verstehen, dass diese Einstellungen wie folgt effektiv für einen bestimmten Modus verhält.</span><span class="sxs-lookup"><span data-stu-id="59f71-140">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="59f71-141">Modus</span><span class="sxs-lookup"><span data-stu-id="59f71-141">Mode</span></span>|<span data-ttu-id="59f71-142">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="59f71-142">AllowUserChat</span></span>|<span data-ttu-id="59f71-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="59f71-143">AllowPrivateCalling</span></span>|<span data-ttu-id="59f71-144">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="59f71-144">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="59f71-145">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="59f71-145">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="59f71-146">TeamsOnly oder Inseln</span><span class="sxs-lookup"><span data-stu-id="59f71-146">TeamsOnly or Islands</span></span>|<span data-ttu-id="59f71-147">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-147">Enabled</span></span>|<span data-ttu-id="59f71-148">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-148">Enabled</span></span>|<span data-ttu-id="59f71-149">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-149">Enabled</span></span>|<span data-ttu-id="59f71-150">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-150">Enabled</span></span>|
|<span data-ttu-id="59f71-151">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="59f71-151">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="59f71-152">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-152">Disabled</span></span>|<span data-ttu-id="59f71-153">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-153">Disabled</span></span>|<span data-ttu-id="59f71-154">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-154">Enabled</span></span>|<span data-ttu-id="59f71-155">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-155">Enabled</span></span>|
|<span data-ttu-id="59f71-156">SfBWithTeamsCollab oder SfBOnly</span><span class="sxs-lookup"><span data-stu-id="59f71-156">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="59f71-157">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-157">Disabled</span></span>|<span data-ttu-id="59f71-158">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-158">Disabled</span></span>|<span data-ttu-id="59f71-159">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-159">Disabled</span></span>|<span data-ttu-id="59f71-160">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="59f71-160">Disabled</span></span>|
||||||

<span data-ttu-id="59f71-161">In naher Zukunft der `Grant-CsTeamsUpgradePolicy` Cmdlet überprüfen Sie die Konfiguration der entsprechenden Einstellungen in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy zu bestimmen, ob diese Einstellungen durch TeamsUpgradePolicy ersetzt werden soll, und wenn dies der Fall ist, wird ein Meldung wird in PowerShell bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="59f71-161">In the near future, the `Grant-CsTeamsUpgradePolicy` cmdlet will check the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings will be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="59f71-162">Wie bereits erwähnt, ist nicht mehr erforderlich, diese anderen Richtlinieneinstellungen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="59f71-162">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="59f71-163">Es folgt ein Beispiel für welche die PowerShell-Warnung aussieht:</span><span class="sxs-lookup"><span data-stu-id="59f71-163">Below is an example of what the PowerShell warning  looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="59f71-164">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="59f71-164">Related topics</span></span>

[<span data-ttu-id="59f71-165">Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="59f71-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




