---
title: Verwalten des schichtbasierten Zugriffs für Mitarbeiter in Teams in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie den schichtbasierten Zugriff in Teams für Mitarbeiter in Firstline in Ihrer Organisation verwalten.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b73fe9b3c4b39e7d3fa7b31427f563c47e5a737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823015"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Verwalten des schichtbasierten Zugriffs für Mitarbeiter in Teams in Teams

> [!IMPORTANT]
> Microsoft StaffHub wurde am 30. Juni 2020 eingestellt. Einige StaffHub-Funktionen werden in Microsoft Teams integriert. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub funktioniert nicht mehr für alle Benutzer am 30. Juni 2020. Jeder, der staffHub zu öffnen versucht, wird in einer Meldung zum Herunterladen von Teams angezeigt. Weitere Informationen finden Sie unter [Microsoft StaffHub wurde eingestellt.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview"></a>Übersicht

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Die Anwesenheit in Microsoft Teams zeigt anderen Benutzern die aktuelle Verfügbarkeit und den aktuellen Status eines Benutzers an. Das Vorhandensein von Mitarbeitern in Firstline ist häufig weniger vorhersehbar als andere Mitarbeiter, da ihre Arbeitszeiten in der Regel nicht jeden Tag gleich sind. Als Administrator können Sie Teams so konfigurieren, dass eine Reihe schichtbasierter Anwesenheitszustände für Die Mitarbeiter in Firstline in Ihrer Organisation angezeigt werden, um anzugeben, wann sie in der Schicht ein- und ausgeschaltet sind.

Diese schichtbasierten Anwesenheitszustände sind einfarbig grün, kennzeichnen "Schicht bei Schicht", "Grauer Kreis" mit "x", "Aus Schicht aus", einfarbiger roter Kreis, der angibt, dass "Beschäftigt" von den Standardeinstellungen der &mdash; ![ ](../../media/flw-presence-on-shift.png) Anwesenheitszustände in Teams getrennt ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; ist. [](../../presence-admins.md) Mit diesen beiden Gruppen von Anwesenheitszuständen können Sie basierend auf ihrer Rolle verschiedene Benutzererfahrungen für Personen in Ihrer Organisation konfigurieren.

Mit schichtbasiertem Zugriff können Sie den Zugriff auf Teams verwalten, wenn Mitarbeiter in Firstline nicht in der Schicht sind. So können Sie beispielsweise in Teams eine Meldung anzeigen, die Mitarbeiter in Firstline bestätigen müssen, bevor sie Teams verwenden können, wenn sie nicht in einer geplanten Schicht arbeiten.  

## <a name="scenario"></a>Szenario

Hier ist ein Beispiel dafür, wie Ihre Organisation den schichtbasierten Zugriff verwalten kann.

Sie haben Mitarbeiter in Firstline in Ihrer Organisation, die nur für Stunden bezahlt werden sollten, die sie an einer Schicht arbeiten, die ihr Vorgesetzter geplant und genehmigt hat. Sie sollten nicht für Zeiten bezahlt werden, die außerhalb einer geplanten Schicht, einschließlich der Verwendung der Teams-App, verbracht wurden. Sie richten eine benutzerdefinierte Meldung ein, die lautet: "Ihre Zeit in Teams, wenn Sie sich nicht in Schichtbetrieb befindet, wird nicht auf die zu zahlenden Stunden angezählt", die angezeigt wird, wenn Mitarbeiter in Firstline versuchen, auf Teams zu zugreifen, wenn Sie nicht in der Schicht sind. Wenn sie sich für die  Verwendung von Teams entscheiden, klicken sie auf "Ich akzeptiere" mit dem Verständnis, dass sie für dieses Mal nicht bezahlt werden.

Außerdem gibt es in Ihrer Organisation Information Workers, die gelohnt werden und nicht in Schichten arbeiten. Sie konfigurieren Ihre Information Workers so, dass sie die standardmäßigen Anwesenheitszustände in Teams verwenden, während Ihre Mitarbeiter in Firstline schichtbasierte Anwesenheitsinformationen erhalten.

## <a name="shift-based-presence-states"></a>Schichtbasierte Anwesenheitszustände

Dies sind die schichtbasierten Anwesenheitszustände.

|Durch die App konfiguriert |Benutzerdefiniert  |Weitere Informationen  |
|---------|---------|---------|
|![Einfarbiges grünes Häkchen, zeigt "Bei Schicht" an](../../media/flw-presence-on-shift.png) Bei Schicht     |         |Automatisches Festlegen am Anfang einer Schicht         |
|![Grauer Kreis mit "x", "Umschalt deaktiviert"](../../media/flw-presence-off-shift.png) Aus Schicht     |         |Automatisches Festlegen am Ende einer Schicht         |
|![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt      | ![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt         |Wird automatisch festgelegt. Kann auch manuell festgelegt werden, wenn sich der Mitarbeiter in Der 1. Reihe befindet.|

## <a name="off-shift-access-to-teams"></a>Off shift access to Teams

Mit diesem Feature können Sie den Zugriff auf Teams verwalten, wenn Mitarbeiter in Firstline nicht schichtschichtig sind. Sie können in Teams festlegen, dass Firstline Workers eine Meldung angezeigt wird, wenn sie in der Schicht auf Teams zugreifen. Mitarbeiter in Firstline müssen auf **"Ich** akzeptiere" klicken, um die Nachricht zu bestätigen, bevor sie Teams verwenden können.

Sie können die Standardnachricht verwenden, aus einer Reihe vordefinierter Nachrichten auswählen oder die Nachricht so anpassen, dass beliebiger Text angezeigt wird. Dies ist die Standardmeldung:

![Screenshot der Standardnachricht](../../media/shifts-presence-message.png)

Sie können auch die Häufigkeit festlegen, mit der die Nachricht angezeigt wird, und eine Toleranzperiode zwischen dem Beginn der ersten oder letzten Schicht und dem Ende der letzten Schicht und dem eingeschränkten Zugriff auf Teams festlegen.

## <a name="manage-shift-based-access"></a>Verwalten des schichtbasierten Zugriffs

Als Administrator steuern Sie mithilfe von Richtlinien die schichtbasierte Anwesenheit für Mitarbeiter in Firstline in Ihrer Organisation. Sie verwalten diese Richtlinien mithilfe der folgenden PowerShell-Cmdlets:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Verwenden Sie New-CsTeamsShiftsPolicy Cmdlet "New-CsTeamsShiftsPolicy", um eine neue Richtlinie zu erstellen, die zu verwendende Richtlinie und anschließend das Cmdlet Grant-CsTeamsShiftsPolicy zum Zuweisen der Richtlinie zu Benutzern fest.

Hier sind einige Beispiele. Ausführliche Informationen zu den einzelnen Richtlinieneinstellungen und -parametern, einschließlich der Liste der vordefinierten Deaktiviert-Schichtnachrichten, aus denen Sie auswählen können, finden Sie unter ["New-CsTeamsShiftsPolicy".](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Beispiel 1

In diesem Beispiel erstellen wir eine neue Richtlinie namens "Off Shift Teams Access Default Message". In dieser Richtlinie ist die schichtbasierte Anwesenheitsanzeige aktiviert, und die Standardmeldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zutritt, wenn er die Schicht deaktiviert hat. Der Benutzer kann Teams in der Schicht deaktiviert verwenden, wenn er die Nachricht annimmt, und die Nachfrist zwischen dem Beginn der ersten oder letzten Schicht und dem eingeschränkten Zugriff beträgt 10 Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Legen Sie die Meldung, die angezeigt werden soll, mithilfe des Parameters **ShiftNoticeMessageType** fest. Eine Liste der vordefinierten Nachrichten, aus der Sie für diesen Parameter auswählen können, finden Sie unter ["New-CsTeamsShiftsPolicy".](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Beispiel 2 

In diesem Beispiel erstellen wir eine neue Richtlinie namens "Off Shift Teams Access Custom Message". In dieser Richtlinie ist die schichtbasierte Anwesenheitsanzeige aktiviert, und es wird immer eine benutzerdefinierte Meldung angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zutritt, wenn er die Schicht deaktiviert hat. Der Benutzer kann Teams in der Schicht deaktiviert verwenden, wenn er die Nachricht annimmt, und die Nachfrist zwischen dem Beginn der ersten oder letzten Schicht und dem eingeschränkten Zugriff beträgt 15 Minuten.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Legen Sie die Meldung, die angezeigt werden soll, mithilfe des Parameters **ShiftNoticeMessageType** fest. Weitere Informationen finden Sie unter ["New-CsTeamsShiftsPolicy".](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Beispiel 3

In diesem Beispiel erstellen wir eine neue Richtlinie namens "Off Shift Teams Access Message1". In dieser Richtlinie ist die schichtbasierte Anwesenheitsanzeige aktiviert, und die folgende vordefinierte Meldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, auf Teams zutritt, wenn er schichtt.

  "Ihr Arbeitgeber autorisiert oder genehmigt nicht die Nutzung seines Netzwerks, seiner Anwendungen, Systeme oder Tools durch nicht ausgenommene oder stündlich angestellte Mitarbeiter während ihrer arbeitsfreie Zeit. Indem Sie annehmen, bestätigen Sie, dass Ihre Nutzung von Teams während der Schichtschaltung nicht autorisiert ist und Dass Sie nicht entschädigt werden." 

Der Benutzer kann Teams verwenden, wenn er die Nachricht annimmt, wenn er die Nachricht annimmt, während die Toleranzperiode zwischen dem Beginn der ersten oder letzten Schicht und dem eingeschränkten Zugriff drei Minuten beträgt.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Legen Sie die Meldung, die angezeigt werden soll, mithilfe des Parameters **ShiftNoticeMessageType** fest. Eine Liste der vordefinierten Nachrichten, aus der Sie für diesen Parameter auswählen können, finden Sie unter ["New-CsTeamsShiftsPolicy".](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Beispiel 4

In diesem Beispiel weisen wir einem Benutzer mit dem Namen "Remy@contoso.com" eine Richtlinie namens "Off Shift Teams Access Custom Message" remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der Schichten-App für Ihre Organisation in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](../../teams-powershell-overview.md)
