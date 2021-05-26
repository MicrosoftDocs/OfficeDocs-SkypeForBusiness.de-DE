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
ms.openlocfilehash: bc1460f93259a9dd3095cf764c38b56ab703bba0
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656048"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Einrichten von Webinaren in Microsoft Teams

Dieser Artikel soll Sie beim Einrichten Ihrer Organisation für Webinare unterstützen.

## <a name="what-are-webinars"></a>Was sind Webinare?

Webinare sind strukturierte Besprechungen, bei denen Kursleiter und Teilnehmer klare Rollen haben, die häufig zu Schulungszwecken oder zu Vertriebs- und Marketing leadgenerierungsszenarien genutzt werden.

Nachdem Sie Webinare in Ihrer Organisation eingerichtet haben, können Ihre Benutzer Webinare planen und die Registrierung für die Teilnehmer öffnen. Im Gegensatz zu traditionellen Besprechungen, die viele Diskussionen und Aufgabenzuweisungen enthalten, sind Webinare für interaktive Präsentationen und Tools für die Teilnehmeranalyse gedacht.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Zulassen, dass Benutzer Webinare mit PowerShell planen

Sie können im Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** die folgenden Attribute verwenden, um Webinare in Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Weitere Informationen zum Cmdlet finden Sie unter [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> Bevor Sie diese Cmdlets ausführen können, müssen Sie mit ihrer Skype for Business PowerShell verbunden sein. Weitere Informationen finden Sie unter [Verwalten Skype for Business Online mit Microsoft 365 oder Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

### <a name="allow-users-to-schedule-webinars"></a>Zulassen, dass Benutzer Webinare planen

Führen Sie dies aus, um Es Benutzern in Ihrer Organisation zu ermöglichen, Webinare zu planen:

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a>Konfigurieren, wer sich für Webinare registrieren kann

Sie können die Registrierung auf Benutzer in Ihrer Organisation beschränken oder sie für alle Benutzer innerhalb und außerhalb Ihres Mandanten öffnen. **WhoCanRegister** ist standardmäßig aktiviert und auf **Jeder festgelegt.** Wenn Sie die Besprechungsregistrierung deaktivieren möchten, legen Sie **AllowMeetingRegistration auf** **False .**

> [!IMPORTANT]
> Beachten Sie, dass **AllowPrivateMeetingScheduling** auf True festgelegt werden **muss,** damit **AllowMeetingRegistration** funktioniert. Darüber hinaus müssen Microsoft-Listen in einem SharePoint. Weitere Informationen finden Sie unter [Steuerelementeinstellungen für Microsoft-Listen.](/sharepoint/control-lists)

**Führen Sie *dies* aus, um nur Benutzern in Ihrer Organisation die Registrierung für Webinare zu ermöglichen:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

Führen Sie dann dies aus:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Führen Sie dies aus, um allen Benutzern, auch anonymen Benutzern, die Registrierung für Webinare zu ermöglichen:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

Führen Sie dann dies aus:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
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
