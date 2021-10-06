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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Erfahren Sie, wie Sie Webinarrichtlinien für Besprechungen Teams verwalten.
ms.openlocfilehash: 35c0cc2ab6c05d123aae45bc0c375cf815db36b4
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138211"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Einrichten von Webinaren in Microsoft Teams

Dieser Artikel soll Sie beim Einrichten Ihrer Organisation für Webinare unterstützen.

## <a name="what-are-webinars"></a>Was sind Webinare?

Webinare sind strukturierte Besprechungen, bei denen Moderatoren und Teilnehmer klare Rollen haben, die häufig zu Schulungszwecken oder zu Vertriebs- und Marketing-Leadgenerierungsszenarien verwendet werden.

Nachdem Sie Webinare in Ihrer Organisation eingerichtet haben, können Ihre Benutzer Webinare planen und die Registrierung für die Teilnehmer öffnen. Im Gegensatz zu herkömmlichen Besprechungen, die viele Diskussionen und Aufgabenzuweisungen enthalten, sind Webinare für interaktive Präsentationen und Tools für die Teilnehmeranalyse gedacht.

> [!IMPORTANT]
> Damit Benutzer Webinare einrichten können, Microsoft Listen sie in einem SharePoint durch Aktivieren der Erstellung persönlicher Listen konfiguriert werden. Weitere Informationen finden Sie unter [Steuerelementeinstellungen für Microsoft Listen.](/sharepoint/control-lists)

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Zulassen, dass Benutzer Webinare im Teams Admin Center planen

Sie können das Teams Admin Center verwenden, um Webinare für Ihre Organisation zu erstellen. Die Richtlinien zum Einrichten von Webinaren finden Sie im Teams Admin Center unter Richtlinien **für**  >  **Besprechungsbesprechungen.**

### <a name="allow-meeting-registration"></a>Besprechungsregistrierung zulassen

Wenn Sie dies aktivieren, können die Benutzer Webinare planen. Diese ist standardmäßig aktiviert. Wenn Sie die Besprechungsregistrierung deaktivieren möchten, legen Sie diese Richtlinie auf **Aus .**

> [!IMPORTANT]
> **Das Planen privater Besprechungen** zulassen muss so sein, dass die Besprechungsregistrierung funktioniert. Diese Richtlinie ist standardmäßig im Admin Center Teams aktiviert. Für Schüler/Studierende in Bildungseinrichtungen ist diese Richtlinie standardmäßig deaktiviert. Weitere Informationen zum Aktivieren der privaten Besprechungsplanung für Schüler/Studierende finden Sie unter Teams für Education [Richtlinien und Richtlinienpakete.](policy-packages-edu.md)

### <a name="who-can-register"></a>Wer kann registriert werden

Wenn Sie Jeder **auswählen,** können sich alle Benutzer, auch anonyme Benutzer, für Webinare registrieren und an ihnen teilnehmen. Wenn Sie **Jeder in der Organisation auswählen,** können sich nur Benutzer in Ihrer Organisation für Webinare registrieren. Wenn die Besprechungsregistrierung deaktiviert ist, steht diese Option nicht zur Verfügung, und niemand kann sich für Webinare registrieren.

> [!NOTE]
> Der Standardwert für das Wer **registriert werden kann,** ist **Jeder in** der Organisation in Education-Mandanten. Weitere Informationen finden Sie unter [Teams für Education Richtlinien-Assistent.](easy-policy-setup-edu.md)

### <a name="allow-engagement-report"></a>Einsatzbericht zulassen

Wenn Sie dies aktivieren, können Organisatoren Berichte dazu anzeigen, wer sich registriert hat und an den von ihnen eingerichteten Webinaren teilgenommen hat. Diese Richtlinie ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Besprechungsrichtlinien in Teams – Einsatzbericht zulassen.](meeting-policies-in-teams-general.md#allow-engagement-report) Informationen zur Endbenutzererfahrung finden Sie unter Anzeigen und Herunterladen der [Anwesenheitsberichte für Besprechungen.](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Zulassen, dass Benutzer Webinare mit PowerShell planen

Sie können im Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** die folgenden Attribute verwenden, um Webinare in Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Weitere Informationen zum Cmdlet finden Sie unter [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> Bevor Sie diese Cmdlets ausführen können, müssen Sie mit Der PowerShell Microsoft Teams sein. Weitere Informationen finden Sie unter [Verwalten von Teams mit Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>Zulassen, dass Benutzer Webinare planen

Sie können die Registrierung auf Benutzer in Ihrer Organisation beschränken oder sie für alle Benutzer innerhalb und außerhalb Ihres Mandanten öffnen. **WhoCanRegister** ist standardmäßig aktiviert und  für die globale **(organisationsweite Standard)-Richtlinie** auf Jeder festgelegt. Wenn Sie die Besprechungsregistrierung deaktivieren möchten, legen Sie **AllowMeetingRegistration auf** **False .**

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** muss auf **True festgelegt sein,** damit **AllowMeetingRegistration** funktioniert.

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

**Führen Sie dies aus, um allen Benutzern, einschließlich anonymer Benutzer, die Registrierung für Webinare zu ermöglichen:**

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

## <a name="configure-webinar-settings"></a>Konfigurieren von Webinareinstellungen

Nachdem Sie Ihre Umgebung für Webinare aktiviert haben, ist keine weitere Administratorverwaltung erforderlich. Die Richtlinie steuert, welche Optionen für Webinarorganisatoren angezeigt werden.

## <a name="related-topics"></a>Verwandte Themen

- [Besprechungsrichtlinien in Teams – Allgemein](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy-Dokumentation](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams für Education Richtlinien-Assistent](easy-policy-setup-edu.md)
