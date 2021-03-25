---
title: Verwenden von PowerShell zum Festlegen von Richtlinien für Liveereignisse
author: cichur
ms.author: v-cichur
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
description: Beispiele für die Verwendung von PowerShell zum Festlegen von Richtlinien in Teams, um zu steuern, wer Liveereignisse in Ihrer Organisation halten kann, und die features, die in den Ereignissen verfügbar sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95b78b520b6978c85715e6dc1c1314ed279a305b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119144"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Verwenden von PowerShell zum Festlegen von Richtlinien für Live-Ereignisse in Microsoft Teams

Sie können die folgenden Windows PowerShell zum Festlegen und Zuweisen von Richtlinieneinstellungen für Liveereignisse in Teams verwenden: 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Hier sind einige Beispiele.

> [!NOTE]
> Bevor Sie diese Cmdlets ausführen können, müssen Sie mit Skype for Business Online PowerShell verbunden sein. Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Microsoft 365 oder Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="allow-users-to-schedule-live-events"></a>Zulassen, dass Benutzer Liveereignisse planen 

> [!NOTE]
> Diese Beispiele sind für In Teams produzierte Ereignisse. Bei Ereignissen, die mit einer externen App oder einem externen Gerät erstellt werden, müssen Sie weitere Schritte ausführen. Weitere Informationen finden Sie unter Aktivieren von Benutzern zum Planen von Ereignissen, die mit einer externen App oder einem [externen Gerät erstellt wurden.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)

**Zulassen, dass ein Benutzer Liveereignisse plant**

Wenn dem Benutzer die globale Richtlinie zugewiesen ist, führen Sie aus, und überprüfen Sie, ob *der Parameter AllowBroadcastScheduling* auf *True festgelegt ist:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Weisen Sie den Benutzer dann der globalen Richtlinie zu, und führen Sie aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Benutzerszenarien
**Sie möchten, dass alle Benutzer in Ihrer Organisation Liveereignisse planen können**

Wenn Benutzern die globale Richtlinie zugewiesen ist, führen Sie aus, und vergewissern Sie sich, dass *AllowBroadcastScheduling* *auf *True festgelegt ist:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Wenn Benutzern eine andere Richtlinie als die globale Richtlinie zugewiesen ist, führen Sie aus, und überprüfen Sie, ob *-AllowBroadcastScheduling* auf *True festgelegt ist:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Sie möchten, dass die Planung von Liveereignissen in Der gesamten Organisation deaktiviert wird.**

Deaktivieren Sie die Planung von Liveereignissen, führen Sie aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Weisen Sie der globalen Richtlinie alle Benutzer in Ihrer Organisation zu, führen Sie aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Sie möchten, dass eine große Anzahl von Benutzern Liveereignisse planen und verhindern kann, dass eine Gruppe von Benutzern sie plant.**

Ausführen und Überprüfen, ob *AllowBroadcastScheduling* auf *True festgelegt ist:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Weisen Sie der globalen Richtlinie dann einen Benutzer oder Benutzer zu, und führen Sie aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Erstellen Sie eine neue Richtlinie, die das Planen von Liveereignissen nicht zulässe, führen Sie aus:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Deaktivieren Sie die Planung von Liveereignissen, führen Sie aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Weisen Sie dieser Richtlinie dann Benutzer zu, und führen Sie aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Sie möchten die Liveereignisplanung für eine große Anzahl von Benutzern deaktivieren und es einer Gruppe von Benutzern ermöglichen, sie zu planen.**

Deaktivieren Sie die Planung von Liveereignissen, führen Sie aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Weisen Sie diese Benutzer dann der globalen Richtlinie zu, und führen Sie aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Erstellen Sie eine Richtlinie, um die Planung von Liveereignissen zu ermöglichen, führen Sie aus:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Aktivieren Sie die Planung von Liveereignissen, führen Sie aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Weisen Sie dieser Richtlinie dann Benutzer zu, und führen Sie aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Festlegen, wer an Liveereignissen teilnehmen kann
 
Legen Sie die globale Richtlinie fest, damit Benutzer Ereignisse erstellen können, an denen jeder teilnehmen kann, einschließlich anonymer Benutzer, und führen Sie aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Festlegen der Aufzeichnungsoption für Liveereignisse
> [!NOTE]
> Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt werden.

Legen Sie die globale Richtlinie so ein, dass die Aufzeichnung für Liveereignisse deaktiviert wird:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Festlegen von Liveuntertiteln und Untertiteln in Liveereignissen
> [!NOTE]
> Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt werden. 

Legen Sie die globale Richtlinie fest, um Liveuntertitel und Untertitel (Transkription) für Ereignisteilnehmer zu aktivieren:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Verwandte Themen
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
- [Übersicht über PowerShell für Microsoft Teams](../teams-powershell-overview.md)