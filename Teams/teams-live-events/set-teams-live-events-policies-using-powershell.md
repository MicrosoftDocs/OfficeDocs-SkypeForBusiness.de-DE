---
title: Verwenden von PowerShell zum Festlegen von live Ereignisse Richtlinien in Microsoft-Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Beispiele zum Festlegen von Richtlinien in Teams, um zu steuern, wer live Ereignisse in Ihrer Organisation und Features enthalten kann mithilfe von PowerShell stehen in der Ereignisse, die sie erstellen
appliesto:
- Microsoft Teams
ms.openlocfilehash: f802c2b67c0a4cd4b0838dd9aeec9c4bbf884968
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "25749168"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="672db-103">Verwenden von PowerShell zum Festlegen von live Ereignisse Richtlinien in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="672db-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="672db-104">Die folgenden Windows PowerShell-Cmdlets können Sie festlegen, und weisen Sie Richtlinieneinstellungen für live Ereignisse in Teams:</span><span class="sxs-lookup"><span data-stu-id="672db-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="672db-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="672db-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="672db-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="672db-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="672db-107">Neue CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="672db-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="672db-108">GRANT-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="672db-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="672db-109">Nachfolgend finden Sie einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="672db-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="672db-110">Zulassen, dass Benutzer live Ereignisse planen</span><span class="sxs-lookup"><span data-stu-id="672db-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="672db-111">In diesen Beispielen werden für Schnellstart Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="672db-111">These examples are for quick start events.</span></span> <span data-ttu-id="672db-112">Für externe Encoder-Ereignisse sind zusätzliche Schritte, die Sie ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="672db-112">For external encoder events, there are additional steps you must do.</span></span> <span data-ttu-id="672db-113">Weitere Informationen finden Sie unter [Aktivieren von Benutzern zum Planen von externen Encoder Ereignisse](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span><span class="sxs-lookup"><span data-stu-id="672db-113">For more information, see [Enable users to schedule external encoder events](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span></span>

<span data-ttu-id="672db-114">**Damit der Benutzer live Ereignisse planen**</span><span class="sxs-lookup"><span data-stu-id="672db-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="672db-115">Wenn der Benutzer die globale Richtlinie zugewiesen ist, führen Sie aus, und stellen Sie sicher, dass *AllowBroadcastScheduling* -Parameter auf *True*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="672db-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="672db-116">Weisen Sie den Benutzer die globale Richtlinie, ausführen:</span><span class="sxs-lookup"><span data-stu-id="672db-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="672db-117">Benutzerszenarien</span><span class="sxs-lookup"><span data-stu-id="672db-117">User scenarios</span></span>
<span data-ttu-id="672db-118">**Sollen alle Benutzer in Ihrer Organisation planen, live Ereignisse können**</span><span class="sxs-lookup"><span data-stu-id="672db-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="672db-119">Wenn Benutzer die globale Richtlinie zugewiesen sind, ausführen, und stellen Sie sicher, *AllowBroadcastScheduling* \* auf *True*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="672db-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="672db-120">Wenn Benutzer eine Richtlinie als globale Richtlinie zugewiesen sind, führen Sie aus, und stellen Sie sicher, dass *- AllowBroadcastScheduling* auf *True*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="672db-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="672db-121">**Live Ereignisse planen in der Organisation deaktiviert werden soll**</span><span class="sxs-lookup"><span data-stu-id="672db-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="672db-122">Deaktivieren Sie live Ereignisse planen, ausführen:</span><span class="sxs-lookup"><span data-stu-id="672db-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="672db-123">Die globale Richtlinie, führen weisen Sie alle Benutzer in Ihrer Organisation zu:</span><span class="sxs-lookup"><span data-stu-id="672db-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="672db-124">**Eine große Anzahl von Benutzern, um planen zu können live Ereignisse und vermeiden, dass eine Gruppe von Benutzern werden sollen**</span><span class="sxs-lookup"><span data-stu-id="672db-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="672db-125">Führen Sie aus, und stellen Sie sicher, dass *AllowBroadcastScheduling* auf *True*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="672db-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="672db-126">Weisen Sie mindestens ein Benutzer die globale Richtlinie, ausführen:</span><span class="sxs-lookup"><span data-stu-id="672db-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="672db-127">Erstellen Sie eine neue Richtlinie, die keine Planung live Ereignisse erlaubt, ausführen:</span><span class="sxs-lookup"><span data-stu-id="672db-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="672db-128">Deaktivieren Sie live Ereignisse planen, ausführen:</span><span class="sxs-lookup"><span data-stu-id="672db-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="672db-129">Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:</span><span class="sxs-lookup"><span data-stu-id="672db-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="672db-130">**Planung für eine große Anzahl von Benutzern live-Ereignis deaktivieren möchten und eine Gruppe von Benutzern so planen sie zulassen**</span><span class="sxs-lookup"><span data-stu-id="672db-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="672db-131">Deaktivieren Sie live Ereignisse planen, ausführen:</span><span class="sxs-lookup"><span data-stu-id="672db-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="672db-132">Die globale Richtlinie, und führen Sie anschließend weisen Sie diese Benutzer zu:</span><span class="sxs-lookup"><span data-stu-id="672db-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="672db-133">Erstellen Sie eine Richtlinie führen Sie zum Zulassen live Ereignisse planen:</span><span class="sxs-lookup"><span data-stu-id="672db-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="672db-134">Planen von live Ereignisse aktivieren, ausführen:</span><span class="sxs-lookup"><span data-stu-id="672db-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="672db-135">Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:</span><span class="sxs-lookup"><span data-stu-id="672db-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="672db-136">Festlegen, die live Ereignisse beitreten können</span><span class="sxs-lookup"><span data-stu-id="672db-136">Set who can join live events</span></span>
 
<span data-ttu-id="672db-137">Legen Sie die globale Richtlinie, damit Benutzer Ereignisse glücklich, einschließlich anonyme Benutzer zu erstellen, können teilnehmen, ausführen:</span><span class="sxs-lookup"><span data-stu-id="672db-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="672db-138">Legen Sie die Aufzeichnung-Option für live Ereignisse</span><span class="sxs-lookup"><span data-stu-id="672db-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="672db-139">Diese Einstellung gilt nur für Ereignisse Schnellstart.</span><span class="sxs-lookup"><span data-stu-id="672db-139">This setting applies only to quick start events.</span></span>

<span data-ttu-id="672db-140">Legen Sie die globale Richtlinie für die Aufzeichnung für live Ereignisse zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="672db-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="672db-141">Festlegen von Umsetzung und Übersetzung in live-Ereignisse (bald verfügbar)</span><span class="sxs-lookup"><span data-stu-id="672db-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="672db-142">Diese Einstellung gilt nur für Ereignisse Schnellstart.</span><span class="sxs-lookup"><span data-stu-id="672db-142">This setting applies only to quick start events.</span></span> 

<span data-ttu-id="672db-143">Legen Sie die globale Richtlinie zum Aktivieren von Umsetzung und Übersetzung für Ereignis Teilnehmer auf:</span><span class="sxs-lookup"><span data-stu-id="672db-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="672db-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="672db-144">Related topics</span></span>
- [<span data-ttu-id="672db-145">Einrichten von für Teams live Ereignisse</span><span class="sxs-lookup"><span data-stu-id="672db-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


