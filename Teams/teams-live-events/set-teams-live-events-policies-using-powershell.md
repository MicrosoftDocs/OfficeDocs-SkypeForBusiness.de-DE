---
title: Verwenden von PowerShell zum Einrichten von Live Ereignisrichtlinien
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Beispiele für die Verwendung von PowerShell zum Festlegen von Richtlinien in Teams, um zu steuern, wer Live Ereignisse in Ihrer Organisation aufnehmen kann und welche Features in den Ereignissen zur Verfügung stehen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e49c2dca91dca56366dd6b8a8ce460547043c120
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369150"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="9b3fb-103">Verwenden von PowerShell zum Festlegen von Richtlinien für Live-Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9b3fb-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="9b3fb-104">Sie können die folgenden Windows PowerShell-Cmdlets verwenden, um in Teams Richtlinieneinstellungen für Live Ereignisse einzurichten und zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="9b3fb-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="9b3fb-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="9b3fb-106">Satz-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="9b3fb-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="9b3fb-107">Neu – CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="9b3fb-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="9b3fb-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="9b3fb-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="9b3fb-109">Neu – CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="9b3fb-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="9b3fb-110">Hier sind einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="9b3fb-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="9b3fb-111">Bevor Sie diese Cmdlets ausführen können, müssen Sie mit Skype for Business Online PowerShell verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="9b3fb-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="9b3fb-112">Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Microsoft 365 oder Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="9b3fb-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="9b3fb-113">Zulassen, dass Benutzer Live Ereignisse planen</span><span class="sxs-lookup"><span data-stu-id="9b3fb-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="9b3fb-114">Diese Beispiele gelten für Ereignisse, die in Teams erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9b3fb-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="9b3fb-115">Bei Ereignissen, die mit einer externen APP oder einem Gerät erstellt wurden, müssen Sie weitere Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b3fb-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="9b3fb-116">Weitere Informationen finden Sie unter [Aktivieren von Benutzern zum Planen von Ereignissen, die mit einer externen APP oder einem externen Gerät erstellt wurden](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="9b3fb-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="9b3fb-117">**Zulassen, dass ein Benutzer Live-Ereignisse plant**</span><span class="sxs-lookup"><span data-stu-id="9b3fb-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="9b3fb-118">Wenn dem Benutzer die globale Richtlinie zugewiesen ist, führen Sie den Parameter *AllowBroadcastScheduling* aus, und überprüfen Sie, ob er auf *true*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="9b3fb-119">Weisen Sie den Benutzer dann der globalen Richtlinie zu, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="9b3fb-120">Benutzerszenarien</span><span class="sxs-lookup"><span data-stu-id="9b3fb-120">User scenarios</span></span>
<span data-ttu-id="9b3fb-121">**Sie möchten, dass alle Benutzer in Ihrer Organisation Live Ereignisse planen können**</span><span class="sxs-lookup"><span data-stu-id="9b3fb-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="9b3fb-122">Wenn Benutzern die globale Richtlinie zugewiesen ist, führen Sie den Vorgang aus, und vergewissern Sie sich, dass *AllowBroadcastScheduling* \* auf *true*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="9b3fb-123">Wenn Benutzer einer anderen Richtlinie als der globalen Richtlinie zugewiesen sind, führen Sie aus, und überprüfen Sie, ob *-AllowBroadcastScheduling* auf *true*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="9b3fb-124">**Sie möchten, dass die Planung von Live Ereignissen in ihrer gesamten Organisation deaktiviert ist.**</span><span class="sxs-lookup"><span data-stu-id="9b3fb-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="9b3fb-125">Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="9b3fb-126">Weisen Sie alle Benutzer in Ihrer Organisation der globalen Richtlinie zu, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="9b3fb-127">**Sie möchten, dass eine große Anzahl von Benutzern in der Lage ist, Live-Ereignisse zu planen und zu verhindern, dass eine Gruppe von Benutzern Sie einplant**</span><span class="sxs-lookup"><span data-stu-id="9b3fb-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="9b3fb-128">Führen Sie aus, und überprüfen Sie, ob *AllowBroadcastScheduling* auf *true*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="9b3fb-129">Weisen Sie dann einen Benutzer oder Benutzer der globalen Richtlinie zu, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="9b3fb-130">Erstellen einer neuen Richtlinie, die das Planen von Live Ereignissen nicht zulässt, führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="9b3fb-131">Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="9b3fb-132">Weisen Sie dann Benutzer dieser Richtlinie zu, führen Sie folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="9b3fb-133">**Sie möchten die Live-Ereignisplanung für eine große Anzahl von Benutzern deaktivieren und es einer Gruppe von Benutzern ermöglichen, Sie zu planen.**</span><span class="sxs-lookup"><span data-stu-id="9b3fb-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="9b3fb-134">Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="9b3fb-135">Weisen Sie diese Benutzer dann der globalen Richtlinie zu, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="9b3fb-136">Erstellen einer Richtlinie zum Zulassen der Terminplanung für Live Ereignisse führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="9b3fb-137">Aktivieren der Terminplanung für Live Ereignisse führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="9b3fb-138">Weisen Sie dann Benutzer dieser Richtlinie zu, führen Sie folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="9b3fb-139">Bestimmen, wer an Live-Events teilnehmen kann</span><span class="sxs-lookup"><span data-stu-id="9b3fb-139">Set who can join live events</span></span>
 
<span data-ttu-id="9b3fb-140">Legen Sie die globale Richtlinie fest, um Benutzern das Erstellen von Ereignissen zu ermöglichen, die jeder, einschließlich anonymer Benutzer, teilnehmen kann:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="9b3fb-141">Einrichten der Aufzeichnungsoption für Live Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9b3fb-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="9b3fb-142">Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9b3fb-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="9b3fb-143">Festlegen der globalen Richtlinie zum Deaktivieren der Aufzeichnung für Live Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="9b3fb-144">Einrichten von Live Beschriftungen und Untertiteln in Live Ereignissen</span><span class="sxs-lookup"><span data-stu-id="9b3fb-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="9b3fb-145">Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9b3fb-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="9b3fb-146">Festlegen der globalen Richtlinie zum Aktivieren von Live Beschriftungen und Untertiteln (Transkription) für Ereignis Teilnehmer:</span><span class="sxs-lookup"><span data-stu-id="9b3fb-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="9b3fb-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9b3fb-147">Related topics</span></span>
- [<span data-ttu-id="9b3fb-148">Einrichten von Teams-Liveereignissen</span><span class="sxs-lookup"><span data-stu-id="9b3fb-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="9b3fb-149">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9b3fb-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

