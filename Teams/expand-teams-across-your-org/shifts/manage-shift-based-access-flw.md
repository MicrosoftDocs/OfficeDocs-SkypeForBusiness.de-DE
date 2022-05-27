---
title: Verwalten des schichtbasierten Zugriffs für Mitarbeiter in Service und Produktion in Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie den schichtbasierten Zugriff in Teams für Mitarbeiter in Service und Produktion in Ihrer Organisation verwalten.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675217"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Verwalten des schichtbasierten Zugriffs für Mitarbeiter in Service und Produktion in Teams
## <a name="overview"></a>Übersicht

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Anwesenheit in Microsoft Teams gibt die aktuelle Verfügbarkeit und den Status eines Benutzers für andere Benutzer an. Die Anwesenheit von Mitarbeitern in Service und Produktion ist oft weniger vorhersagbar als andere Mitarbeiter, da ihre Arbeitszeiten in der Regel nicht jeden Tag identisch sind. Als Administrator können Sie Teams so konfigurieren, dass eine Reihe schichtbasierter Anwesenheitszustände für Mitarbeiter in Service und Produktion in Ihrer Organisation angezeigt werden, um anzugeben, wann sie im Schichtbetrieb sind.

Diese schichtbasierte Anwesenheitsstatus&mdash;![einfarbiges grünes Häkchen, gibt "Bei Schicht" an.](../../media/flw-presence-on-shift.png) **Bei der Umschalttaste**, ![grauer Kreis mit x, gibt die Umschalttaste "Aus" an.](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams. Mit diesen beiden Gruppen von Anwesenheitszuständen können Sie unterschiedliche Erfahrungen für Personen in Ihrer Organisation basierend auf ihrer Rolle konfigurieren.

Mit schichtbasiertem Zugriff können Sie den Zugriff auf Teams verwalten, wenn Mitarbeiter in Service und Produktion außerhalb der Schicht arbeiten. Sie können beispielsweise festlegen, dass Teams eine Meldung anzeigt, die Mitarbeiter in Service und Produktion bestätigen müssen, bevor sie Teams verwenden können, wenn sie sich nicht in einer geplanten Schicht befinden.  

## <a name="scenario"></a>Szenario

Hier ist ein Beispiel, wie Ihre Organisation den schichtbasierten Zugriff verwalten kann.

Sie haben Mitarbeiter in Service und Produktion in Ihrer Organisation, die nur für Stunden bezahlt werden sollten, die sie in einer Schicht arbeiten, die ihr Vorgesetzter geplant und genehmigt hat. Sie sollten nicht für die Zeit bezahlt werden, die außerhalb einer geplanten Schicht verbracht wurde, einschließlich der Verwendung der Teams-App. Sie richten eine benutzerdefinierte Meldung ein, die besagt: "Ihre Zeit am Teams wenn die Schicht deaktiviert ist, zählt nicht zu den zahlbaren Stunden", die angezeigt wird, wenn Mitarbeiter in Service und Produktion versuchen, auf Teams zuzugreifen, wenn sie außerhalb der Schicht sind. Wenn sie sich für Teams entscheiden, klicken sie auf **"Ich stimme** zu" mit dem Verständnis, dass sie für diese Zeit nicht bezahlt werden.

Außerdem verfügen Sie über Informationsmitarbeiter in Ihrer Organisation, die gehältert sind und keine Schichten arbeiten. Sie konfigurieren Ihre Information Worker so, dass sie die Standardmäßige Anwesenheitsstatus in Teams verwenden, während Sie Ihren Mitarbeitern in Service und Produktion schichtbasierte Anwesenheitsinformationen zuweisen.

## <a name="shift-based-presence-states"></a>Schichtbasierte Anwesenheitszustände

Hier sind die schichtbasierten Anwesenheitszustände.

|Durch die App konfiguriert |Benutzerdefiniert  |Weitere Informationen  |
|---------|---------|---------|
|![Einfarbiges grünes Häkchen, zeigt "Bei Umschalt" an.](../../media/flw-presence-on-shift.png) Bei Schicht     |         |Automatisches Festlegen zu Beginn einer Schicht         |
|![Grauer Kreis mit x, zeigt die Aus-Umschalttaste an](../../media/flw-presence-off-shift.png) Aus der Schicht     |         |Automatisches Festlegen am Ende einer Schicht         |
|![Ein durchgehender roter Kreis zeigt an: beschäftigt.](../../media/flw-presence-busy.png) Beschäftigt      | ![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt         |Wird automatisch festgelegt. Kann auch manuell festgelegt werden, wenn sich der Mitarbeiter in Service und Produktion im Schichtbetrieb befindet.|

## <a name="off-shift-access-to-teams"></a>Deaktivieren des Schichtzugriffs auf Teams

Mit diesem Feature können Sie den Zugriff auf Teams verwalten, wenn Mitarbeiter in Service und Produktion außerHalb der Schicht sind. Sie können festlegen, dass Teams Mitarbeitern in Service und Produktion eine Meldung anzeigt, wenn sie auf Teams zugreifen, wenn sie außerhalb der Schicht sind. Mitarbeiter in Service und Produktion müssen auf **"Ich stimme zu"** klicken, um die Nachricht zu bestätigen, bevor sie Teams verwenden können.

Sie können die Standardnachricht verwenden, aus einer Reihe vordefinierter Nachrichten auswählen oder die Nachricht so anpassen, dass der gewünschte Text angezeigt wird. Dies ist die Standardmeldung:

![Screenshot der Standardnachricht.](../../media/shifts-presence-message.png)

Sie können auch die Häufigkeit festlegen, wenn die Nachricht angezeigt wird, und eine Karenzzeit zwischen dem Start der ersten Schicht oder dem Ende der letzten Schicht und dem Eingeschränkten Zugriff auf Teams festlegen.

## <a name="manage-shift-based-access"></a>Verwalten des schichtbasierten Zugriffs

Als Administrator verwenden Sie Richtlinien, um schichtbasierte Anwesenheitsinformationen für Mitarbeiter in Service und Produktion in Ihrer Organisation zu steuern. Sie verwalten diese Richtlinien mithilfe der folgenden PowerShell-Cmdlets:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Verwenden Sie das cmdlet New-CsTeamsShiftsPolicy, um eine neue Richtlinie zu erstellen, die gewünschten Richtlinieneinstellungen festzulegen, und verwenden Sie dann das cmdlet Grant-CsTeamsShiftsPolicy, um die Richtlinie Benutzern zuzuweisen.

Hier sind einige Beispiele. Ausführliche Informationen zu den einzelnen Richtlinieneinstellungen und Parametern, einschließlich der Liste der vordefinierten Off-Shift-Nachrichten, aus denen Sie auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Beispiel 1

In diesem Beispiel erstellen wir eine neue Richtlinie namens Off Shift Teams Access Default Message. In dieser Richtlinie ist die schichtbasierte Anwesenheit aktiviert, und die Standardmeldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zugreift, wenn die Schicht deaktiviert ist. Der Benutzer kann Teams verwenden, wenn er die Schicht deaktiviert hat, wenn er die Nachricht annimmt, und die Nachfrist zwischen dem Start der ersten Schicht oder der letzten Schicht und der Einschränkung des Zugriffs beträgt 10 Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Verwenden Sie den **Parameter ShiftNoticeMessageType** , um die Anzuzeigende Nachricht festzulegen. Eine Liste der vordefinierten Nachrichten, aus denen Sie für diesen Parameter auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Beispiel 2 

In diesem Beispiel erstellen wir eine neue Richtlinie namens Off Shift Teams Access Custom Message. In dieser Richtlinie ist die schichtbasierte Anwesenheit aktiviert, und jedes Mal wird eine benutzerdefinierte Meldung angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zugreift, wenn er die Schicht deaktiviert hat. Der Benutzer kann Teams verwenden, wenn er die Schicht deaktiviert hat, wenn er die Nachricht akzeptiert, und die Nachfrist zwischen dem Start der ersten Schicht oder der letzten Schicht und der Einschränkung des Zugriffs beträgt 15 Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Verwenden Sie den **Parameter ShiftNoticeMessageType** , um die Anzuzeigende Nachricht festzulegen. Weitere Informationen finden Sie unter [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Beispiel 3

In diesem Beispiel erstellen wir eine neue Richtlinie namens Off Shift Teams Access Message1. In dieser Richtlinie ist die schichtbasierte Anwesenheit aktiviert, und die folgende vordefinierte Meldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zugreift, wenn er die Schicht deaktiviert hat.

  "Ihr Arbeitgeber autorisiert oder genehmigt nicht die Nutzung seines Netzwerks, seiner Anwendungen, Systeme oder Tools durch nicht freigestellte oder stündliche Mitarbeiter während ihrer arbeitsfreien Zeiten. Mit der Annahme bestätigen Sie, dass Ihre Nutzung von Teams während der Schichtzeit nicht autorisiert ist und Sie nicht entschädigt werden." 

Der Benutzer kann Teams verwenden, wenn er die Schicht deaktiviert hat, wenn er die Nachricht akzeptiert, und die Nachfrist zwischen dem Start der ersten Schicht oder der letzten Schicht und der Einschränkung des Zugriffs beträgt drei Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Verwenden Sie den **Parameter ShiftNoticeMessageType** , um die Anzuzeigende Nachricht festzulegen. Eine Liste der vordefinierten Nachrichten, aus denen Sie für diesen Parameter auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Beispiel 4

In diesem Beispiel weisen wir eine Richtlinie namens Off Shift Teams Access Custom Message einem Benutzer namens remy@contoso.com zu.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der "Schichten"-App für Ihre Organisation in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](../../teams-powershell-overview.md)