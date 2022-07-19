---
title: Verwenden von PowerShell zum Festlegen von Richtlinien für Liveereignisse
author: mkbond007
ms.author: mabond
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Beispiele für die Verwendung von PowerShell zum Festlegen von Richtlinien in Teams, um zu steuern, wer Liveereignisse in Ihrer Organisation abhalten kann, und die in den Ereignissen verfügbaren Features.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e0d46c0675bd8b810f8dbce8585661184fbef74f
ms.sourcegitcommit: 791d0a341ff873145fa893ece05055729b0b8d50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2022
ms.locfileid: "66838840"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Verwenden von PowerShell zum Festlegen von Richtlinien für Live-Ereignisse in Microsoft Teams

Sie können die folgenden Windows PowerShell-Cmdlets verwenden, um Richtlinieneinstellungen für Liveereignisse in Teams festzulegen und zuzuweisen: 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Hier sind einige Beispiele.

> [!NOTE]
> Bevor Sie diese Cmdlets ausführen können, müssen Sie mit Skype for Business Online PowerShell verbunden sein. Weitere Informationen finden [Sie unter Verwalten von Skype for Business Online mit Microsoft 365 oder Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Zulassen, dass Benutzer Liveereignisse planen 

> [!NOTE]
> Diese Beispiele gelten für Ereignisse, die in Teams erstellt wurden. Für Ereignisse, die mit einer externen App oder einem externen Gerät erstellt werden, müssen Sie zusätzliche Schritte ausführen. Weitere Informationen finden Sie unter [Aktivieren von Benutzern zum Planen von Ereignissen, die mit einer externen App oder einem externen Gerät erstellt wurden](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Zulassen, dass ein Benutzer Liveereignisse plant**

Wenn dem Benutzer die globale Richtlinie zugewiesen ist, führen Sie den Parameter *AllowBroadcastScheduling aus, und vergewissern Sie sich, dass der Parameter "AllowBroadcastScheduling**" auf "True"* festgelegt ist:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Weisen Sie den Benutzer dann der globalen Richtlinie zu, und führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Benutzerszenarien
**Sie möchten, dass alle Benutzer in Ihrer Organisation Liveereignisse planen können.**

Wenn Benutzern die globale Richtlinie zugewiesen ist, führen Sie die *Option "AllowBroadcastScheduling* *" aus, und überprüfen Sie, ob "AllowBroadcastScheduling* *" auf "True"* festgelegt ist:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Wenn Benutzern eine andere Richtlinie als der globalen Richtlinie zugewiesen ist, führen Sie die Option *"-AllowBroadcastScheduling" aus, und überprüfen Sie, ob "-AllowBroadcastScheduling* " auf *"True"* festgelegt ist:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Sie möchten, dass die Planung von Liveereignissen in Ihrer Organisation deaktiviert wird.**

Deaktivieren Sie die Planung von Liveereignissen, führen Sie Folgendes aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Weisen Sie alle Benutzer in Ihrer Organisation der globalen Richtlinie zu, führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Sie möchten, dass eine große Anzahl von Benutzern Liveereignisse planen und verhindern kann, dass eine Gruppe von Benutzern sie plant**

Führen Sie die *Option "AllowBroadcastScheduling" aus, und überprüfen Sie, ob "AllowBroadcastScheduling* " auf *"True"* festgelegt ist:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Weisen Sie dann der globalen Richtlinie einen oder mehrere Benutzer zu, und führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Erstellen Sie eine neue Richtlinie, die die Planung von Liveereignissen nicht zulässt, führen Sie Folgendes aus:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Deaktivieren Sie die Planung von Liveereignissen, führen Sie Folgendes aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Weisen Sie dann dieser Richtlinie Benutzer zu, führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Sie möchten die Planung von Liveereignissen für eine große Anzahl von Benutzern deaktivieren und es einer Gruppe von Benutzern ermöglichen, sie zu planen.**

Deaktivieren Sie die Planung von Liveereignissen, führen Sie Folgendes aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Weisen Sie diese Benutzer dann der globalen Richtlinie zu, und führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Erstellen Sie eine Richtlinie, um die Planung von Liveereignissen zuzulassen, führen Sie Folgendes aus:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Aktivieren Sie die Planung von Liveereignissen, führen Sie Folgendes aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Weisen Sie dann dieser Richtlinie Benutzer zu, führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Festlegen, wer an Liveereignissen teilnehmen kann
 
Legen Sie die globale Richtlinie fest, damit Benutzer Ereignisse erstellen können, an denen jeder teilnehmen kann, einschließlich anonymer Benutzer:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Festlegen der Aufzeichnungsoption für Liveereignisse
> [!NOTE]
> Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt wurden.

Legen Sie die globale Richtlinie zum Deaktivieren der Aufzeichnung für Liveereignisse fest:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Festlegen von Liveuntertiteln und Untertiteln in Liveereignissen
> [!NOTE]
> Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt wurden. 

Legen Sie die globale Richtlinie fest, um Liveuntertitel und Untertitel (Transkription) für Ereignisteilnehmer zu aktivieren:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Verwandte Themen
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
- [Übersicht über PowerShell für Microsoft Teams](../teams-powershell-overview.md)