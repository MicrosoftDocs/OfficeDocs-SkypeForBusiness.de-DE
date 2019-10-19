---
title: Verwenden von PowerShell zum Festlegen von Richtlinien für Live-Ereignisse in Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Beispiele für die Verwendung von PowerShell zum Festlegen von Richtlinien in Teams, um zu steuern, wer Live Ereignisse in Ihrer Organisation aufnehmen kann, und Features, die in den von Ihnen erstellten Ereignissen zur Verfügung stehen
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f96adcf4aa40b93b89b99013b9bc5ca466c25b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "37570168"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="5d1f7-103">Verwenden von PowerShell zum Festlegen von Richtlinien für Live-Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d1f7-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="5d1f7-104">Sie können die folgenden Windows PowerShell-Cmdlets verwenden, um in Teams Richtlinieneinstellungen für Live Ereignisse einzurichten und zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="5d1f7-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="5d1f7-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="5d1f7-106">Satz-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="5d1f7-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="5d1f7-107">Neu – CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="5d1f7-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="5d1f7-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="5d1f7-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="5d1f7-109">Hier sind einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="5d1f7-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="5d1f7-110">Zulassen, dass Benutzer Live Ereignisse planen</span><span class="sxs-lookup"><span data-stu-id="5d1f7-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="5d1f7-111">Diese Beispiele gelten für Ereignisse, die in Teams erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5d1f7-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="5d1f7-112">Bei Ereignissen, die mit einer externen APP oder einem Gerät erstellt wurden, müssen Sie weitere Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="5d1f7-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="5d1f7-113">Weitere Informationen finden Sie unter [Aktivieren von Benutzern zum Planen von Ereignissen, die mit einer externen APP oder einem externen Gerät erstellt wurden](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="5d1f7-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="5d1f7-114">**Zulassen, dass ein Benutzer Live-Ereignisse plant**</span><span class="sxs-lookup"><span data-stu-id="5d1f7-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="5d1f7-115">Wenn dem Benutzer die globale Richtlinie zugewiesen ist, führen Sie den Parameter *AllowBroadcastScheduling* aus, und überprüfen Sie, ob er auf *true*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="5d1f7-116">Weisen Sie den Benutzer dann der globalen Richtlinie zu, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="5d1f7-117">Benutzerszenarien</span><span class="sxs-lookup"><span data-stu-id="5d1f7-117">User scenarios</span></span>
<span data-ttu-id="5d1f7-118">**Sie möchten, dass alle Benutzer in Ihrer Organisation Live Ereignisse planen können**</span><span class="sxs-lookup"><span data-stu-id="5d1f7-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="5d1f7-119">Wenn Benutzern die globale Richtlinie zugewiesen ist, führen Sie den Vorgang aus, und vergewissern Sie sich, dass *AllowBroadcastScheduling* \* auf *true*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="5d1f7-120">Wenn Benutzer einer anderen Richtlinie als der globalen Richtlinie zugewiesen sind, führen Sie aus, und überprüfen Sie, ob *-AllowBroadcastScheduling* auf *true*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="5d1f7-121">**Sie möchten, dass die Planung von Live Ereignissen in ihrer gesamten Organisation deaktiviert ist.**</span><span class="sxs-lookup"><span data-stu-id="5d1f7-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="5d1f7-122">Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="5d1f7-123">Weisen Sie alle Benutzer in Ihrer Organisation der globalen Richtlinie zu, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="5d1f7-124">**Sie möchten, dass eine große Anzahl von Benutzern in der Lage ist, Live-Ereignisse zu planen und zu verhindern, dass eine Gruppe von Benutzern Sie einplant**</span><span class="sxs-lookup"><span data-stu-id="5d1f7-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="5d1f7-125">Führen Sie aus, und überprüfen Sie, ob *AllowBroadcastScheduling* auf *true*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="5d1f7-126">Weisen Sie dann einen Benutzer oder Benutzer der globalen Richtlinie zu, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="5d1f7-127">Erstellen einer neuen Richtlinie, die das Planen von Live Ereignissen nicht zulässt, führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="5d1f7-128">Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="5d1f7-129">Weisen Sie dann Benutzer dieser Richtlinie zu, führen Sie folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="5d1f7-130">**Sie möchten die Live-Ereignisplanung für eine große Anzahl von Benutzern deaktivieren und es einer Gruppe von Benutzern ermöglichen, Sie zu planen.**</span><span class="sxs-lookup"><span data-stu-id="5d1f7-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="5d1f7-131">Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="5d1f7-132">Weisen Sie diese Benutzer dann der globalen Richtlinie zu, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="5d1f7-133">Erstellen einer Richtlinie zum Zulassen der Terminplanung für Live Ereignisse führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="5d1f7-134">Aktivieren der Terminplanung für Live Ereignisse führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="5d1f7-135">Weisen Sie dann Benutzer dieser Richtlinie zu, führen Sie folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="5d1f7-136">Bestimmen, wer an Live-Events teilnehmen kann</span><span class="sxs-lookup"><span data-stu-id="5d1f7-136">Set who can join live events</span></span>
 
<span data-ttu-id="5d1f7-137">Legen Sie die globale Richtlinie fest, um Benutzern das Erstellen von Ereignissen zu ermöglichen, die jeder, einschließlich anonymer Benutzer, teilnehmen kann:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="5d1f7-138">Einrichten der Aufzeichnungsoption für Live Ereignisse</span><span class="sxs-lookup"><span data-stu-id="5d1f7-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="5d1f7-139">Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5d1f7-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="5d1f7-140">Festlegen der globalen Richtlinie zum Deaktivieren der Aufzeichnung für Live Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="5d1f7-141">Einrichten von Live Beschriftungen und Untertiteln in Live Ereignissen</span><span class="sxs-lookup"><span data-stu-id="5d1f7-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="5d1f7-142">Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5d1f7-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="5d1f7-143">Festlegen der globalen Richtlinie zum Aktivieren von Live Beschriftungen und Untertiteln (Transkription) für Ereignis Teilnehmer:</span><span class="sxs-lookup"><span data-stu-id="5d1f7-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="5d1f7-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5d1f7-144">Related topics</span></span>
- [<span data-ttu-id="5d1f7-145">Einrichten von Teams-Liveereignissen</span><span class="sxs-lookup"><span data-stu-id="5d1f7-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


