---
title: Verwalten des schichtbasierten Zugriffs für Frontline-Mitarbeiter in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie den schichtbasierten Zugriff in Teams für Frontline-Mitarbeiter in Ihrer Organisation verwalten.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092543"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Verwalten des schichtbasierten Zugriffs für Frontline-Mitarbeiter in Teams

> [!IMPORTANT]
> Mit Wirkung zum 30. Juni 2020 wurde Microsoft StaffHub eingestellt. Einige StaffHub-Funktionen werden in Microsoft Teams integriert. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub wurde am 30. Juni 2020 für alle Benutzer eingestellt. Jedem, der versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, in der er aufgefordert wird, Teams herunterzuladen. Weitere Informationen finden Sie unter [Microsoft StaffHub wurde eingestellt](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Übersicht

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Die Anwesenheit in Microsoft Teams gibt die aktuelle Verfügbarkeit und den Status eines Benutzers für andere Benutzer an. Die Anwesenheit von Frontline-Mitarbeitern ist häufig weniger vorhersehbar als andere Mitarbeiter, da ihre Arbeitszeiten normalerweise nicht jeden Tag gleich sind. Als Administrator können Sie Teams so konfigurieren, dass eine Reihe schichtbasierter Anwesenheitszustände für die Mitarbeiter an der Frontlinie in Ihrer Organisation angezeigt wird, um anzugeben, wann sie sich in der Schicht befinden oder nicht.

Diese schichtbasierten Anwesenheitszustände Einfarbiges grünes Häkchen, gibt Bei Schicht bei Schicht , Grauer Kreis mit x an, gibt Aus Schicht aus Schicht aus, Einfarbiger roter Kreis, gibt an, dass Beschäftigt beschäftigt getrennt vom Standardsatz von &mdash; ![ Anwesenheitszuständen ](../../media/flw-presence-on-shift.png)  ![ in Teams ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; sind. [](../../presence-admins.md) Mit diesen beiden Gruppen von Anwesenheitszuständen können Sie basierend auf ihrer Rolle unterschiedliche Benutzererfahrungen für Personen in Ihrer Organisation konfigurieren.

Mit schichtbasiertem Zugriff können Sie den Zugriff auf Teams verwalten, wenn Mitarbeiter in der Frontline nicht im Schichtbetrieb sind. Sie können beispielsweise Festlegen, dass Teams eine Meldung anzeigen kann, die Mitarbeiter in der Frontline bestätigen müssen, bevor sie Teams verwenden können, wenn sie sich nicht in einer geplanten Schicht befindet.  

## <a name="scenario"></a>Szenario

Hier ist ein Beispiel dafür, wie Ihre Organisation den schichtbasierten Zugriff verwalten kann.

Sie verfügen über Frontline-Mitarbeiter in Ihrer Organisation, die nur für Stunden bezahlt werden sollten, die sie in einer Schicht arbeiten, die ihr Vorgesetzter geplant und genehmigt hat. Sie sollten nicht für die Zeit bezahlt werden, die sie außerhalb einer geplanten Schicht verbracht haben, einschließlich der Verwendung der Teams-App. Sie richten eine benutzerdefinierte Meldung ein, die lautet: "Ihre Zeit in Teams, wenn sie nicht in der Schicht ist, zählt nicht zu den zu zahlenden Stunden", die angezeigt wird, wenn Frontline-Mitarbeiter versuchen, in Der Schicht auf Teams zu zugreifen. Wenn sie Teams verwenden, klicken sie auf Ich akzeptiere **mit** dem Verständnis, dass sie für dieses Mal nicht bezahlt werden.

Sie haben auch Mitarbeiter in Ihrer Organisation, die Angestellte sind und keine Schichten arbeiten. Sie konfigurieren Ihre Mitarbeiter so, dass sie die Standardpräsenzzustände in Teams verwenden, während Sie Ihren Frontline-Mitarbeitern schichtbasierte Anwesenheitsinformationen geben.

## <a name="shift-based-presence-states"></a>Schichtbasierte Anwesenheitszustände

Hier sind die schichtbasierten Anwesenheitszustände.

|Durch die App konfiguriert |Benutzerdefiniert  |Weitere Informationen  |
|---------|---------|---------|
|![Einfarbiges grünes Häkchen, zeigt Bei Schicht an](../../media/flw-presence-on-shift.png) Im Schichtbetrieb     |         |Automatisches Festlegen am Anfang einer Schicht         |
|![Grauer Kreis mit x, zeigt Umschalttaste aus](../../media/flw-presence-off-shift.png) Ausschalten     |         |Automatisches Festlegen am Ende einer Schicht         |
|![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt      | ![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt         |Automatisches Festlegen. Kann auch manuell festgelegt werden, wenn sich der Frontline-Worker im Schichtbetrieb befindet.|

## <a name="off-shift-access-to-teams"></a>Off-Shift-Zugriff auf Teams

Mit diesem Feature können Sie den Zugriff auf Teams verwalten, wenn Mitarbeiter an der Frontlinie nicht im Schichtbetrieb sind. Sie können Festlegen, dass Teams eine Nachricht an "Frontline Workers" zeigt, wenn diese in der Schicht auf Teams zugreifen. Mitarbeiter an der Frontlinie müssen auf **Ich akzeptiere klicken,** um die Nachricht zu bestätigen, bevor sie Teams verwenden können.

Sie können die Standardnachricht verwenden, aus einer Reihe vordefinierter Nachrichten auswählen oder die Nachricht so anpassen, dass der von Ihnen angezeigte Text angezeigt wird. Dies ist die Standardmeldung:

![Screenshot der Standardnachricht](../../media/shifts-presence-message.png)

Sie können auch die Häufigkeit festlegen, in der die Nachricht angezeigt wird, und einen Nachfristzeitraum festlegen, zwischen dem Beginn der ersten oder letzten Schicht und dem eingeschränkten Zugriff auf Teams.

## <a name="manage-shift-based-access"></a>Verwalten des schichtbasierten Zugriffs

Als Administrator steuern Sie mithilfe von Richtlinien die schichtbasierte Anwesenheit von Frontline-Mitarbeitern in Ihrer Organisation. Sie verwalten diese Richtlinien mithilfe der folgenden PowerShell-Cmdlets:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Verwenden Sie New-CsTeamsShiftsPolicy-Cmdlet, um eine neue Richtlinie zu erstellen, die richtlinieneinstellungen, die Sie verwenden möchten, und verwenden Sie dann das Grant-CsTeamsShiftsPolicy-Cmdlet, um die Richtlinie Benutzern zuzuordnen.

Hier sind einige Beispiele. Ausführliche Informationen zu den einzelnen Richtlinieneinstellungen und -parametern, einschließlich der Liste vordefinierter Off-Shift-Nachrichten, aus denen Sie auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Beispiel 1

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen Off Shift Teams Access Default Message. In dieser Richtlinie ist schichtbasierte Anwesenheit aktiviert, und die Standardmeldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zutritt, wenn er die Schicht abschaltet. Der Benutzer kann Teams verwenden, wenn die Schicht deaktiviert ist, wenn er die Nachricht annimmt, und die Nachfrist zwischen dem Start der ersten Schicht oder dem Ende der letzten Schicht und dem eingeschränkten Zugriff beträgt 10 Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Verwenden Sie **den Parameter ShiftNoticeMessageType,** um die Meldung zu festlegen, die Sie anzeigen möchten. Eine Liste der vordefinierten Nachrichten, aus der Sie für diesen Parameter auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Beispiel 2 

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen Off Shift Teams Access Custom Message. In dieser Richtlinie ist schichtbasierte Anwesenheit aktiviert, und jedes Mal, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zutritt, wenn er die Schicht abschaltet, wird eine benutzerdefinierte Nachricht angezeigt. Der Benutzer kann Teams verwenden, wenn die Schicht deaktiviert ist, wenn er die Nachricht annimmt, und die Nachfrist zwischen dem Start der ersten Schicht oder dem Ende der letzten Schicht und dem eingeschränkten Zugriff beträgt 15 Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Verwenden Sie **den Parameter ShiftNoticeMessageType,** um die Meldung zu festlegen, die Sie anzeigen möchten. Weitere Informationen finden Sie unter [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Beispiel 3

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen Off Shift Teams Access Message1. In dieser Richtlinie ist schichtbasierte Anwesenheit aktiviert, und die folgende vordefinierte Meldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zutritt, wenn er die Schicht abschaltet.

  "Ihr Arbeitgeber autorisiert oder genehmigt nicht die Verwendung seines Netzwerks, seiner Anwendungen, Systeme oder Tools durch nicht ausgenommene oder stündlich beschäftigte Mitarbeiter während ihrer arbeitsfreie Zeit. Indem Sie akzeptieren, bestätigen Sie, dass Ihre Verwendung von Teams während der Schicht nicht autorisiert ist und Sie nicht entschädigt werden." 

Der Benutzer kann Teams verwenden, wenn die Schicht deaktiviert ist, wenn er die Nachricht annimmt, und die Nachfrist zwischen dem Start der ersten Schicht oder dem Ende der letzten Schicht und dem eingeschränkten Zugriff beträgt drei Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Verwenden Sie **den Parameter ShiftNoticeMessageType,** um die Meldung zu festlegen, die Sie anzeigen möchten. Eine Liste der vordefinierten Nachrichten, aus der Sie für diesen Parameter auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Beispiel 4

In diesem Beispiel weisen wir einem Benutzer namens "Off Shift Teams Access Custom Message" eine Richtlinie namens Off Shift Teams Access remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der "Schichten"-App für Ihre Organisation in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](../../teams-powershell-overview.md)