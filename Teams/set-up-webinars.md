---
title: Einrichten von Webinaren in Microsoft Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Erfahren Sie, wie Sie Webinarrichtlinien für Teams-Besprechungen verwalten.
ms.openlocfilehash: 26863b26f960b50d81fa1d98090c3616d5b492a7
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706482"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Einrichten von Webinaren in Microsoft Teams

Dieser Artikel hilft Ihnen beim Einrichten Ihrer Organisation zum Hosten von Webinaren.

## <a name="what-are-webinars"></a>Was sind Webinare?

Webinare sind strukturierte Besprechungen, bei denen Referenten und Teilnehmer klare Rollen haben, die häufig für Schulungszwecke oder Vertriebs- und Marketing-Leadgenerierungsszenarien verwendet werden.

Nachdem Sie Webinare in Ihrer Organisation eingerichtet haben, können Ihre Benutzer Webinare planen und die Registrierung für Teilnehmer öffnen. Im Gegensatz zu herkömmlichen Besprechungen, die viele Diskussionen und Aufgabenzuweisungen enthalten, sind Webinare für interaktive Präsentationen gedacht und bieten Tools für die Teilnehmeranalyse.

> [!IMPORTANT]
> Damit Benutzer Webinare einrichten können, müssen Microsoft Listen in SharePoint konfiguriert werden, indem die Erstellung persönlicher Listen aktiviert wird. Weitere Informationen finden Sie unter [Steuerelementeinstellungen für Microsoft Listen](/sharepoint/control-lists).

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Zulassen, dass Benutzer Webinare im Teams Admin Center planen

Sie können das Teams Admin Center verwenden, um Webinare für Ihre Organisation einzurichten. Die Richtlinien zum Einrichten von Webinaren finden Sie im Teams Admin Center unter den Richtlinien für **Besprechungsbesprechungen** > .

### <a name="meeting-registration"></a>Besprechungsregistrierung

Wenn Sie diese Option aktivieren, können Benutzer Webinare planen. Standardmäßig ist dies aktiviert. Wenn Sie die Besprechungsregistrierung deaktivieren möchten, legen Sie diese Richtlinie auf **"Aus**" fest.

> [!IMPORTANT]
> **Die Planung privater Besprechungen** muss aktiviert sein, damit die Besprechungsregistrierung funktioniert. Standardmäßig ist diese Richtlinie im Teams Admin Center aktiviert. Für Schüler in Bildungsmandanten ist diese Richtlinie standardmäßig deaktiviert. Weitere Informationen zum Aktivieren der privaten Besprechungsplanung für Kursteilnehmer finden Sie [unter Teams für Education Richtlinien und Richtlinienpakete](policy-packages-edu.md).

### <a name="who-can-register"></a>Wer kann sich registrieren?

Wenn Sie **"Jeder**" auswählen, können sich alle Benutzer, einschließlich anonymer Benutzer, für Webinare registrieren und daran teilnehmen. Wenn Sie **"Jeder in der Organisation**" auswählen, können sich nur Benutzer in Ihrer Organisation für Webinare registrieren. Wenn die Besprechungsregistrierung deaktiviert ist, ist diese Option nicht verfügbar, und niemand kann sich für Webinare registrieren.

> [!NOTE]
> Der Standardwert für **"Wer kann sich registrieren"** ist **"Jeder in der Organisation** in Bildungsmandanten". Weitere Informationen finden Sie [unter Teams für Education Richtlinien-Assistenten](easy-policy-setup-edu.md).

### <a name="engagement-report"></a>Einsatzbericht

Wenn dies aktiviert ist, können Organisatoren Berichte sehen, wer sich registriert hat und an den von ihnen eingerichteten Webinaren teilgenommen hat. Diese Richtlinie ist standardmäßig aktiviert. Weitere Informationen finden Sie [unter "Besprechungsrichtlinien in Teams – Einsatzbericht"](meeting-policies-in-teams-general.md#engagement-report). Informationen zur Endbenutzererfahrung finden Sie unter [Anzeigen und Herunterladen von Anwesenheitsberichten zu Besprechungen](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US).

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Zulassen, dass Benutzer Webinare mithilfe von PowerShell planen

Sie können die folgenden Attribute im cmdlet Windows PowerShell **Set-CsTeamsMeetingPolicy** verwenden, um Webinare in Teams einzurichten.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Weitere Informationen zum Cmdlet finden Sie unter [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) .

> [!NOTE]
> Bevor Sie diese Cmdlets ausführen können, müssen Sie mit Microsoft Teams PowerShell verbunden sein. Weitere Informationen finden [Sie unter Verwalten von Teams mit Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Zulassen, dass Benutzer Webinare planen

Sie können die Registrierung nur auf Benutzer in Ihrer Organisation beschränken oder sie für alle Personen innerhalb und außerhalb Ihres Mandanten öffnen. **WhoCanRegister** ist standardmäßig aktiviert und für die **globale Richtlinie (organisationsweiter Standard)** auf **"Jeder**" festgelegt. Wenn Sie die Besprechungsregistrierung deaktivieren möchten, legen Sie **AllowMeetingRegistration** auf **"False"** fest.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** muss auf **"True** " festgelegt sein **, damit AllowMeetingRegistration** funktioniert.

1. Aktivieren der Besprechungsregistrierung

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Aktivieren der Planung privater Besprechungen

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Konfigurieren, wer sich für Webinare registrieren kann

***Nur Benutzern* in Ihrer Organisation erlauben, sich für Webinare zu registrieren**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Führen Sie Folgendes aus, um allen Personen, einschließlich anonymer Benutzer, die Registrierung für Webinare zu ermöglichen:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Wenn die anonyme Teilnahme in den Besprechungseinstellungen deaktiviert ist, können anonyme Benutzer nicht an Webinaren teilnehmen. Weitere Informationen und die Aktivierung dieser Einstellung finden Sie [unter "Besprechungseinstellungen" in Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Sammeln der Besprechungsteilnahme

Mit dem Parameter **AllowEngagementReport** können Sie sehen, wer Webinare registriert und besucht hat. Diese Richtlinie ist standardmäßig aktiviert. Führen Sie zum Deaktivieren den folgenden Befehl in PowerShell aus:

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>Konfigurieren von Webinareinstellungen

Nachdem Sie Ihre Umgebung für Webinare aktiviert haben, ist keine weitere Administratorverwaltung erforderlich. Die Richtlinie steuert, welche Optionen für Webinarorganisatoren angezeigt werden.

## <a name="related-topics"></a>Verwandte Themen

- [Besprechungsrichtlinien in Teams – Allgemein](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy-Dokumentation](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams für Education-Richtlinien-Assistent](easy-policy-setup-edu.md)
