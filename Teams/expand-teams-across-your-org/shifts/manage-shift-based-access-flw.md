---
title: Verwalten Sie den schichtbasierten Zugriff für Mitarbeiter in frontline Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie den schichtbasierten Zugriff in ihrem Teams für Frontline-Mitarbeiter in Ihrer Organisation verwalten.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e2bcffd23a8603acbb0954ddb6a24dad9000332
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584609"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Verwalten Sie den schichtbasierten Zugriff für Mitarbeiter in frontline Teams

> [!IMPORTANT]
> Mit Wirkung zum 30. Juni 2020 wurde Microsoft StaffHub eingestellt. Einige StaffHub-Funktionen werden in Microsoft Teams integriert. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub wurde am 30. Juni 2020 für alle Benutzer eingestellt. Jedem, der versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, in der er aufgefordert wird, Teams herunterzuladen. Weitere Informationen finden Sie unter [Microsoft StaffHub wurde eingestellt](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Übersicht

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Die Anwesenheit in Microsoft Teams zeigt die aktuelle Verfügbarkeit und den Status eines Benutzers für andere Benutzer an. Das Vorhandensein von Mitarbeitern in der Front ist häufig weniger vorhersehbar als andere Mitarbeiter, da ihre Arbeitszeiten in der Regel nicht jeden Tag gleich sind. Als Administrator können Sie Teams so konfigurieren, dass eine Reihe von schichtbasierten Anwesenheitszuständen für die Frontline-Mitarbeiter in Ihrer Organisation angezeigt werden, um anzugeben, wann sie in der Schicht ein- und ausgeschaltet sind.

Diese schichtbasierten Anwesenheitszustände Einfarbiges grünes Häkchen, gibt Bei Schicht Bei Schicht, Grauer Kreis mit x an, gibt Off Schicht Aus, Einfarbiger roter Kreis, gibt an, dass Beschäftigt Beschäftigt sind getrennt von den Standardeinstellung von &mdash; ![ Anwesenheitszuständen ](../../media/flw-presence-on-shift.png)  ![ in ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) Mit diesen beiden Gruppen von Anwesenheitszuständen können Sie basierend auf ihrer Rolle verschiedene Erfahrungen für Personen in Ihrer Organisation konfigurieren.

Mit schichtbasiertem Zugriff können Sie den Zugriff auf Mitarbeiter Teams, wenn Mitarbeiter an der Vorderlinie nicht schichtschichtig sind. Beispielsweise können Sie festlegen, dass Teams eine Meldung anzeigen, die Mitarbeiter in der Frontlinie bestätigen müssen, bevor sie Teams, wenn sie sich nicht in einer geplanten Schicht befindet, verwenden können.  

## <a name="scenario"></a>Szenario

Hier ist ein Beispiel dafür, wie Ihre Organisation den schichtbasierten Zugriff verwalten kann.

Sie haben Mitarbeiter in der Frontlinie in Ihrer Organisation, die nur für Stunden bezahlt werden sollten, die sie an einer von ihrem Vorgesetzten geplanten und genehmigten Schicht arbeiten. Sie sollten nicht für Zeiten bezahlt werden, die außerhalb einer geplanten Schicht arbeiten, was auch die Verwendung der App Teams beinhaltet. Sie richten eine benutzerdefinierte Meldung ein, die lautet: "Ihre Zeit am Teams, wenn Sie sich nicht im Schichtbetrieb befindet, zählt nicht zu den zu zahlenden Stunden". Diese Meldung wird angezeigt, wenn Mitarbeiter in der Einsatzleitung versuchen, auf Teams zu greifen, wenn Sie nicht über Schicht schichtt. Wenn sie sich für die Verwendung  Teams, klicken sie auf Ich akzeptiere mit dem Verständnis, dass sie für dieses Mal nicht bezahlt werden.

Es gibt auch Information-Workers in Ihrer Organisation, die gelohnt werden und nicht in Schichten arbeiten. Sie konfigurieren Ihre Information-Workers so, dass sie die standardmäßigen Anwesenheitszustände in Teams während Sie Ihren Mitarbeitern in der Frontline schichtbasierte Anwesenheitsinformationen geben.

## <a name="shift-based-presence-states"></a>Schichtbasierte Anwesenheitszustände

Dies sind die schichtbasierten Anwesenheitszustände.

|Durch die App konfiguriert |Benutzerdefiniert  |Weitere Informationen  |
|---------|---------|---------|
|![Einfarbiges grünes Häkchen, zeigt Bei Schicht an](../../media/flw-presence-on-shift.png) In Schicht     |         |Automatisches Festlegen am Anfang einer Schicht         |
|![Grauer Kreis mit x, kennzeichnet "Umschalttaste aus"](../../media/flw-presence-off-shift.png) Umschalttaste aus der Schicht     |         |Automatisches Festlegen am Ende einer Schicht         |
|![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt      | ![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt         |Automatisches Festlegen. Kann auch manuell festgelegt werden, wenn der Frontline-Worker sich in der Schicht befindet.|

## <a name="off-shift-access-to-teams"></a>Deaktivieren des Schichtzugriffs auf Teams

Mit diesem Feature können Sie den Zugriff auf Mitarbeiter Teams, wenn Mitarbeiter an vorder frontline nicht schichtt sind. Sie können festlegen Teams, dass eine Nachricht an die Mitarbeiter in der Front angezeigt wird, wenn diese bei Teams Schicht darauf zugreifen. Mitarbeiter in der Frontlinie müssen **auf Ich akzeptiere** klicken, um die Nachricht zu bestätigen, bevor sie Ihre Teams.

Sie können die Standardnachricht verwenden, aus einer Reihe vordefinierter Nachrichten auswählen oder die Nachricht so anpassen, dass beliebiger Text angezeigt wird. Dies ist die Standardmeldung:

![Screenshot der Standardnachricht](../../media/shifts-presence-message.png)

Sie können auch die Häufigkeit festlegen, mit der die Nachricht angezeigt wird, und eine Toleranzperiode zwischen dem Beginn der ersten oder letzten Schicht und dem Ende der letzten Schicht und dem eingeschränkten Zugriff auf die Teams festlegen.

## <a name="manage-shift-based-access"></a>Verwalten des schichtbasierten Zugriffs

Als Administrator verwenden Sie Richtlinien, um die schichtbasierte Anwesenheit für Mitarbeiter in der Frontline in Ihrer Organisation zu steuern. Sie verwalten diese Richtlinien mithilfe der folgenden PowerShell-Cmdlets:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Verwenden Sie New-CsTeamsShiftsPolicy-Cmdlet "New-CsTeamsShiftsPolicy", um eine neue Richtlinie zu erstellen, die von Ihnen verwendeten Richtlinieneinstellungen fest, und verwenden Sie dann das Grant-CsTeamsShiftsPolicy-Cmdlet, um die Richtlinie Benutzern zuzuordnen.

Hier sind einige Beispiele. Ausführliche Informationen zu den einzelnen Richtlinieneinstellungen und -parametern, einschließlich der Liste der vordefinierten Nachrichten für deaktivierte Schichten, aus denen Sie auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Beispiel 1

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen Off Shift Teams Access Default Message. In dieser Richtlinie ist die schichtbasierte Anwesenheitsanzeige aktiviert, und die Standardmeldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf die Anwesenheitsinformationen zu Teams, wenn die Schicht deaktiviert ist. Der Benutzer kann Teams verwenden, wenn er die Nachricht annimmt, wenn er die Nachricht annimmt, und die Toleranzperiode zwischen dem Beginn der ersten oder letzten Schicht und dem Ende der letzten Schicht und dem eingeschränkten Zugriff beträgt 10 Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Verwenden Sie **den Parameter ShiftNoticeMessageType,** um die Meldung fest, die angezeigt werden soll. Eine Liste der vordefinierten Nachrichten, aus der Sie für diesen Parameter auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Beispiel 2 

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen Off Shift Teams Access Custom Message. In dieser Richtlinie ist die schichtbasierte Anwesenheitsanzeige aktiviert, und jedes Mal, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf die Schicht Teams, wird eine benutzerdefinierte Meldung angezeigt. Der Benutzer kann Teams verwenden, wenn er die Nachricht annimmt, wenn er die Nachricht annimmt, und die Nachfrist zwischen dem Beginn der ersten oder letzten Schicht und dem Ende der letzten Schicht und dem eingeschränkten Zugriff auf 15 Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Verwenden Sie **den Parameter ShiftNoticeMessageType,** um die Meldung fest, die angezeigt werden soll. Weitere Informationen finden Sie unter [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Beispiel 3

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen Off Shift Teams Access Message1. In dieser Richtlinie ist die schichtbasierte Anwesenheitsanzeige aktiviert, und die folgende vordefinierte Meldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf die Anwesenheitsinformationen zu Teams, wenn er die Schicht deaktiviert hat.

  "Ihr Arbeitgeber autorisiert oder genehmigt nicht die Nutzung seines Netzwerks, seiner Anwendungen, Systeme oder Tools durch mitarbeiterfreie oder stundenfreie Mitarbeiter während ihrer arbeitsfreie Zeit. Durch Ihre Annahme erkennen Sie an, dass Teams Nutzung von Verlagerungen nicht autorisiert ist und Sie nicht entschädigt werden." 

Der Benutzer kann Teams verwenden, wenn er die Nachricht annimmt, wenn er die Nachricht annimmt, und die Nachfrist zwischen dem Beginn der ersten oder letzten Schicht und dem Ende der letzten Schicht und dem eingeschränkten Zugriff auf drei Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Verwenden Sie **den Parameter ShiftNoticeMessageType,** um die Meldung fest, die angezeigt werden soll. Eine Liste der vordefinierten Nachrichten, aus der Sie für diesen Parameter auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Beispiel 4

In diesem Beispiel weisen wir einem Benutzer mit dem Namen "Teams" eine Richtlinie namens "Benutzerdefinierte Access-Nachricht" remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der "Schichten"-App für Ihre Organisation in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](../../teams-powershell-overview.md)