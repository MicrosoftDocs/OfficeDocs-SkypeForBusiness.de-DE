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
ms.openlocfilehash: 4d5f1cceb42afd2be92aedcd0a40af4e23650512
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140646"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Verwenden von PowerShell zum Festlegen von Richtlinien für Live-Ereignisse in Microsoft Teams

Sie können die folgenden Windows PowerShell-Cmdlets verwenden, um in Teams Richtlinieneinstellungen für Live Ereignisse einzurichten und zuzuweisen: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Satz-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Neu – CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Hier sind einige Beispiele.

> [!NOTE]
> Bevor Sie diese Cmdlets ausführen können, müssen Sie mit Skype for Business Online PowerShell verbunden sein. Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Zulassen, dass Benutzer Live Ereignisse planen 

> [!NOTE]
> Diese Beispiele gelten für Ereignisse, die in Teams erstellt wurden. Bei Ereignissen, die mit einer externen APP oder einem Gerät erstellt wurden, müssen Sie weitere Schritte ausführen. Weitere Informationen finden Sie unter [Aktivieren von Benutzern zum Planen von Ereignissen, die mit einer externen APP oder einem externen Gerät erstellt wurden](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Zulassen, dass ein Benutzer Live-Ereignisse plant**

Wenn dem Benutzer die globale Richtlinie zugewiesen ist, führen Sie den Parameter *AllowBroadcastScheduling* aus, und überprüfen Sie, ob er auf *true*festgelegt ist:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Weisen Sie den Benutzer dann der globalen Richtlinie zu, führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Benutzerszenarien
**Sie möchten, dass alle Benutzer in Ihrer Organisation Live Ereignisse planen können**

Wenn Benutzern die globale Richtlinie zugewiesen ist, führen Sie den Vorgang aus, und vergewissern Sie sich, dass *AllowBroadcastScheduling* * auf *true*festgelegt ist:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Wenn Benutzer einer anderen Richtlinie als der globalen Richtlinie zugewiesen sind, führen Sie aus, und überprüfen Sie, ob *-AllowBroadcastScheduling* auf *true*festgelegt ist:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Sie möchten, dass die Planung von Live Ereignissen in ihrer gesamten Organisation deaktiviert ist.**

Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Weisen Sie alle Benutzer in Ihrer Organisation der globalen Richtlinie zu, führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Sie möchten, dass eine große Anzahl von Benutzern in der Lage ist, Live-Ereignisse zu planen und zu verhindern, dass eine Gruppe von Benutzern Sie einplant**

Führen Sie aus, und überprüfen Sie, ob *AllowBroadcastScheduling* auf *true*festgelegt ist:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Weisen Sie dann einen Benutzer oder Benutzer der globalen Richtlinie zu, führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Erstellen einer neuen Richtlinie, die das Planen von Live Ereignissen nicht zulässt, führen Sie folgende Aktionen aus:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Weisen Sie dann Benutzer dieser Richtlinie zu, führen Sie folgende Aktion aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Sie möchten die Live-Ereignisplanung für eine große Anzahl von Benutzern deaktivieren und es einer Gruppe von Benutzern ermöglichen, Sie zu planen.**

Deaktivieren Sie die Live-Terminplanung, führen Sie folgende Aktionen aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Weisen Sie diese Benutzer dann der globalen Richtlinie zu, führen Sie Folgendes aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Erstellen einer Richtlinie zum Zulassen der Terminplanung für Live Ereignisse führen Sie folgende Aktionen aus:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Aktivieren der Terminplanung für Live Ereignisse führen Sie folgende Aktionen aus:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Weisen Sie dann Benutzer dieser Richtlinie zu, führen Sie folgende Aktion aus:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Bestimmen, wer an Live-Events teilnehmen kann
 
Legen Sie die globale Richtlinie fest, um Benutzern das Erstellen von Ereignissen zu ermöglichen, die jeder, einschließlich anonymer Benutzer, teilnehmen kann:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Einrichten der Aufzeichnungsoption für Live Ereignisse
> [!NOTE]
> Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt wurden.

Festlegen der globalen Richtlinie zum Deaktivieren der Aufzeichnung für Live Ereignisse:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Einrichten von Live Beschriftungen und Untertiteln in Live Ereignissen
> [!NOTE]
> Diese Einstellung gilt nur für Ereignisse, die in Teams erstellt wurden. 

Festlegen der globalen Richtlinie zum Aktivieren von Live Beschriftungen und Untertiteln (Transkription) für Ereignis Teilnehmer:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Verwandte Themen
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
- [Übersicht über PowerShell für Microsoft Teams](../teams-powershell-overview.md)

