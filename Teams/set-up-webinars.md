---
title: Einrichten von Webinaren in Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Erfahren Sie, wie Sie Webinarrichtlinien für Besprechungen Teams verwalten.
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926747"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Einrichten von Webinaren in Microsoft Teams

Dieser Artikel soll Sie beim Einrichten Ihrer Organisation für Webinare unterstützen.

## <a name="what-are-webinars"></a>Was sind Webinare?

Webinare sind strukturierte Besprechungen, bei denen Moderatoren und Teilnehmer klare Rollen haben, die häufig zu Schulungszwecken oder zu Vertriebs- und Marketing-Leadgenerierungsszenarien verwendet werden.

Nachdem Sie Webinare in Ihrer Organisation eingerichtet haben, können Ihre Benutzer Webinare planen und die Registrierung für die Teilnehmer öffnen. Im Gegensatz zu traditionellen Besprechungen, die viele Diskussionen und Aufgabenzuweisungen enthalten, sind Webinare für interaktive Präsentationen und Tools für die Teilnehmeranalyse gedacht.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Zulassen, dass Benutzer Webinare mit PowerShell planen

Sie können im Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** die folgenden Attribute verwenden, um Webinare in Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Weitere Informationen zum Cmdlet finden Sie unter [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> Bevor Sie diese Cmdlets ausführen können, müssen Sie mit powerShell Microsoft Teams verbunden sein. Weitere Informationen finden Sie unter [Verwalten von Teams mit Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>Zulassen, dass Benutzer Webinare planen

Sie können die Registrierung auf Benutzer in Ihrer Organisation beschränken oder sie für alle Benutzer innerhalb und außerhalb Ihres Mandanten öffnen. **WhoCanRegister** ist standardmäßig aktiviert und auf **Jeder festgelegt.** Wenn Sie die Besprechungsregistrierung deaktivieren möchten, legen Sie **AllowMeetingRegistration auf** **False .**

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** muss auf **True festgelegt sein,** damit **AllowMeetingRegistration** funktioniert. Darüber hinaus müssen Microsoft-Listen in einem SharePoint. Weitere Informationen finden Sie unter [Steuerelementeinstellungen für Microsoft-Listen.](/sharepoint/control-lists)

1. Aktivieren der Besprechungsregistrierung

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Aktivieren der privaten Besprechungsplanung

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Konfigurieren, wer sich für Webinare registrieren kann

***Zulassen,* dass sich nur Benutzer in Ihrer Organisation für Webinare registrieren**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Führen Sie dies aus, um allen Benutzern, auch anonymen Benutzern, die Registrierung für Webinare zu ermöglichen:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Wenn die anonyme Teilnahme in den Besprechungseinstellungen deaktiviert ist, können anonyme Benutzer nicht an Webinaren teilnehmen. Weitere Informationen zum Aktivieren dieser Einstellung finden Sie unter [Besprechungseinstellungen in Teams.](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>Erfassen der Teilnahme an Besprechungen

Wenn Sie möchten, dass Organisatoren analysieren, wer Webinare registriert und teilgenommen hat, müssen Sie die Richtlinie **AllowEngagementReport** aktivieren. Führen Sie dazu den folgenden Befehl in PowerShell aus.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>Konfigurieren von Webinareinstellungen

Nachdem Sie Ihre Umgebung für Webinare aktiviert haben, ist keine weitere Administratorverwaltung erforderlich. Die Richtlinie steuert, welche Optionen für Webinarorganisatoren angezeigt werden.

## <a name="related-topics"></a>Verwandte Themen

- [Besprechungsrichtlinien in Teams – Allgemein](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy-Dokumentation](/powershell/module/skype/set-csteamsmeetingpolicy)
