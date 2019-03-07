---
title: Verwenden von PowerShell zum Festlegen von Richtlinien für Live-Ereignisse in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Beispiele zum Festlegen von Richtlinien in Teams, um zu steuern, wer live Ereignisse in Ihrer Organisation und Features enthalten kann mithilfe von PowerShell stehen in der Ereignisse, die sie erstellen
appliesto:
- Microsoft Teams
ms.openlocfilehash: 23cf75c8e764920a2d77c3bbe6c0cb3711c22f04
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459628"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Verwenden von PowerShell zum Festlegen von Richtlinien für Live-Ereignisse in Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Die folgenden Windows PowerShell-Cmdlets können Sie festlegen, und weisen Sie Richtlinieneinstellungen für live Ereignisse in Teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Neue CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [GRANT-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Nachfolgend finden Sie einige Beispiele.

## <a name="allow-users-to-schedule-live-events"></a>Zulassen, dass Benutzer live Ereignisse planen 

> [!NOTE]
> In diesen Beispielen werden für Schnellstart Ereignisse. Für externe Encoder-Ereignisse sind zusätzliche Schritte, die Sie ausführen müssen. Weitere Informationen finden Sie unter [Aktivieren von Benutzern zum Planen von externen Encoder Ereignisse](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).

**Damit der Benutzer live Ereignisse planen**

Wenn der Benutzer die globale Richtlinie zugewiesen ist, führen Sie aus, und stellen Sie sicher, dass *AllowBroadcastScheduling* -Parameter auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Weisen Sie den Benutzer die globale Richtlinie, ausführen:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Benutzerszenarien
**Sollen alle Benutzer in Ihrer Organisation planen, live Ereignisse können**

Wenn Benutzer die globale Richtlinie zugewiesen sind, ausführen, und stellen Sie sicher, *AllowBroadcastScheduling* * auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Wenn Benutzer eine Richtlinie als globale Richtlinie zugewiesen sind, führen Sie aus, und stellen Sie sicher, dass *- AllowBroadcastScheduling* auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Live Ereignisse planen in der Organisation deaktiviert werden soll**

Deaktivieren Sie live Ereignisse planen, ausführen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Die globale Richtlinie, führen weisen Sie alle Benutzer in Ihrer Organisation zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Eine große Anzahl von Benutzern, um planen zu können live Ereignisse und vermeiden, dass eine Gruppe von Benutzern werden sollen**

Führen Sie aus, und stellen Sie sicher, dass *AllowBroadcastScheduling* auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Weisen Sie mindestens ein Benutzer die globale Richtlinie, ausführen:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Erstellen Sie eine neue Richtlinie, die keine Planung live Ereignisse erlaubt, ausführen:
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Deaktivieren Sie live Ereignisse planen, ausführen:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Planung für eine große Anzahl von Benutzern live-Ereignis deaktivieren möchten und eine Gruppe von Benutzern so planen sie zulassen**

Deaktivieren Sie live Ereignisse planen, ausführen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Die globale Richtlinie, und führen Sie anschließend weisen Sie diese Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Erstellen Sie eine Richtlinie führen Sie zum Zulassen live Ereignisse planen:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Planen von live Ereignisse aktivieren, ausführen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Festlegen, die live Ereignisse beitreten können
 
Legen Sie die globale Richtlinie, damit Benutzer Ereignisse glücklich, einschließlich anonyme Benutzer zu erstellen, können teilnehmen, ausführen:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Legen Sie die Aufzeichnung-Option für live Ereignisse
> [!NOTE]
> Diese Einstellung gilt nur für Ereignisse Schnellstart.

Legen Sie die globale Richtlinie für die Aufzeichnung für live Ereignisse zu deaktivieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a>Festlegen von Umsetzung und Übersetzung in live-Ereignisse (bald verfügbar)
> [!NOTE]
> Diese Einstellung gilt nur für Ereignisse Schnellstart. 

Legen Sie die globale Richtlinie zum Aktivieren von Umsetzung und Übersetzung für Ereignis Teilnehmer auf:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Verwandte Themen
- [Einrichten von für Teams live Ereignisse](set-up-for-teams-live-events.md)


