---
title: Verwalten des Schicht basierten Zugriffs für Mitarbeiter von First-work in Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie den Schicht basierten Zugriff in Teams für First-worker in Ihrer Organisation verwalten können.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01180f95766412b82d9df7986c3667298f24d5b4
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486852"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Verwalten des Schicht basierten Zugriffs für Mitarbeiter von First-work in Teams

> [!IMPORTANT]
> Gültig 30. Juni 2020, Microsoft StaffHub wurde eingestellt. Einige StaffHub-Funktionen werden in Microsoft Teams integriert. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub funktionierte am 30. Juni 2020 nicht mehr für alle Benutzer. Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, in der Sie zum Herunterladen von Teams geleitet werden. Weitere Informationen finden Sie unter [Microsoft StaffHub wurde eingestellt](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Übersicht

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Anwesenheit in Microsoft Teams zeigt die aktuelle Verfügbarkeit und den Status eines Benutzers für andere Benutzer an. Das vorhanden sein von First-work-Mitarbeitern ist oft weniger vorhersehbar als andere Mitarbeiter, da ihre Arbeitszeiten in der Regel nicht täglich identisch sind. Als Administrator können Sie Teams so konfigurieren, dass eine Reihe von Schicht basierten Anwesenheitsstatus für die Mitarbeiter der ersten Zeile in Ihrer Organisation angezeigt werden, um anzugeben, wann diese ein-und ausgeschaltet sind.

Diese Schicht basierten Anwesenheitsstatus zeigt ein vollständiges, &mdash; ![ grünes Häkchen, das bei UMSCHALT ](../../media/flw-presence-on-shift.png) **auf Schicht**, ![ grauer Kreis mit x, zeigt die UMSCHALT- ](../../media/flw-presence-off-shift.png) **aus-Schicht**, vollständiger ![ roter Kreis, zeigt an, dass beschäftigt ](../../media/flw-presence-busy.png) **beschäftigte** &mdash; getrennt von der [Standardgruppe der Anwesenheitsstatus](../../presence-admins.md) in Teams sind. Mit diesen zwei Gruppen von Anwesenheitsstatus können Sie unterschiedliche Erfahrungen für Personen in Ihrer Organisation basierend auf ihrer Rolle konfigurieren.

Mit einem Schicht basierten Zugriff können Sie den Zugriff auf Teams verwalten, wenn die Arbeitszeiten von First-Worker deaktiviert sind. So können Sie beispielsweise Teams so einrichten, dass eine Meldung angezeigt wird, die Mitarbeiter von First-Worker bestätigen müssen, bevor Sie Teams verwenden können, wenn Sie sich nicht in einer geplanten Schicht befinden.  

## <a name="scenario"></a>Szenario

Im folgenden finden Sie ein Beispiel dafür, wie Ihre Organisation den Schicht basierten Zugriff verwalten kann.

Sie haben Mitarbeiter in Ihrer Organisation, die nur Stunden lang bezahlt werden, wenn Sie an einer vom Manager geplanten und genehmigten Schicht arbeiten. Sie sollten nicht für die Zeit bezahlt werden, die außerhalb einer geplanten Schichtarbeit verbrachte, die die Verwendung der Teams-App umfasst. Sie richten eine benutzerdefinierte Nachricht ein, die besagt, dass "Ihre Zeit für Teams, wenn ein-aus-Schicht nicht zu den zu zahlenden Stunden gezählt wird", die angezeigt wird, wenn die Mitarbeiter von First-work versuchen, auf Teams zuzugreifen. Wenn Sie sich für die Verwendung von Teams entscheiden, klicken Sie auf **Ich akzeptiere** mit dem Verständnis, dass Sie für diese Zeit nicht bezahlt werden.

Sie haben auch Informationsmitarbeiter in Ihrer Organisation, die Angestellte sind und keine Schichten arbeiten. Sie konfigurieren Ihre Information Worker so, dass Sie die Standard Anwesenheitsstatus in Teams verwenden, während Sie Ihren Mitarbeitern auf Schicht Basis eine schichtbasierte Anwesenheit geben.

## <a name="shift-based-presence-states"></a>Schichtbasierte Anwesenheitsstatus

Hier sind die Schicht basierten Anwesenheitsstatus.

|Durch die App konfiguriert |Benutzerdefiniert  |Weitere Informationen  |
|---------|---------|---------|
|![Vollständiges grünes Häkchen, zeigt die UMSCHALTTASTE an](../../media/flw-presence-on-shift.png) Bei Schicht     |         |Wird automatisch am Anfang einer Schicht gesetzt         |
|![Grauer Kreis mit x, zeigt die UMSCHALTTASTE an](../../media/flw-presence-off-shift.png) Aus-Schicht     |         |Automatisches setzen am Ende einer Schicht         |
|![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt      | ![Ein gefüllter roter Kreis zeigt an: beschäftigt](../../media/flw-presence-busy.png) Beschäftigt         |Automatisch eingestellt. Kann auch manuell eingestellt werden, wenn sich die erste Arbeitskraft in der Schicht befindet.|

## <a name="off-shift-access-to-teams"></a>Off-Shift-Zugriff auf Teams

Mit diesem Feature können Sie den Zugriff auf Teams verwalten, wenn die Arbeit von Mitarbeitern in der ersten Schicht deaktiviert ist. Sie können Teams so einrichten, dass eine Nachricht angezeigt wird, wenn die Mitarbeiter auf Teams zugreifen, wenn Sie die UMSCHALTTASTE deaktivieren. First-Worker-Mitarbeiter müssen auf **Ich akzeptiere** klicken, um die Nachricht zu bestätigen, bevor Sie Teams verwenden können.

Sie können die Standardmeldung verwenden, aus einer Reihe vordefinierter Nachrichten auswählen oder die Nachricht anpassen, um den gewünschten Text anzuzeigen. Die folgende Standardmeldung lautet:

![Screenshot der Standardnachricht](../../media/shifts-presence-message.png)

Sie können auch die Häufigkeit einstellen, wenn die Nachricht angezeigt wird, und einen Kulanzzeitraum zwischen dem Ende der ersten Schicht oder der letzten Schicht und dem Zugriff auf Teams einstellen.

## <a name="manage-shift-based-access"></a>Verwalten des Schicht basierten Zugriffs

Als Administrator verwenden Sie Richtlinien, um die schichtbasierte Anwesenheit für First-work-Mitarbeiter in Ihrer Organisation zu steuern. Sie verwalten diese Richtlinien mithilfe der folgenden PowerShell-Cmdlets:

- [Neu – CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Satz-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Verwenden Sie das New-CsTeamsShiftsPolicy-Cmdlet, um eine neue Richtlinie zu erstellen, die gewünschten Richtlinieneinstellungen festzulegen, und verwenden Sie dann das Cmdlet Grant-CsTeamsShiftsPolicy, um die Richtlinie Benutzern zuzuweisen.

Hier sind einige Beispiele. Detaillierte Informationen zu den einzelnen Richtlinieneinstellungen und-Parametern, einschließlich der Liste der vordefinierten off-Schicht-Nachrichten, aus denen Sie auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Beispiel 1

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen "aus Schicht Teams" auf Standardnachricht zugreifen. In dieser Richtlinie wird die Verschiebungs basierte Anwesenheit aktiviert, und die Standardmeldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, bei ausgeschalteter Schicht auf Teams zugreift. Der Benutzer kann Teams verwenden, wenn die Umschaltfläche deaktiviert ist, wenn er die Nachricht akzeptiert, und die Nachfrist zwischen dem Beginn der ersten Schicht oder der letzten Schicht und dem Zeitpunkt, zu dem der Zugriff eingeschränkt ist, 10 Minuten beträgt.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Verwenden Sie den **ShiftNoticeMessageType** -Parameter, um die Nachricht festzulegen, die Sie anzeigen möchten. Eine Liste der vordefinierten Nachrichten, die Sie für diesen Parameter auswählen können, finden Sie unter [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Beispiel 2 

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen "aus Schicht Teams Zugriff auf benutzerdefinierte Nachricht". In dieser Richtlinie wird die schichtbasierte Anwesenheit aktiviert, und es wird jedes Mal eine benutzerdefinierte Meldung angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, bei ausgeschalteter Schicht auf Teams zugreift. Der Benutzer kann Teams verwenden, wenn die Umschaltfläche deaktiviert ist, wenn er die Nachricht akzeptiert, und die Nachfrist zwischen dem Beginn der ersten Schicht oder der letzten Schicht und dem Zeitpunkt, zu dem der Zugriff eingeschränkt ist, 15 Minuten beträgt.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Verwenden Sie den **ShiftNoticeMessageType** -Parameter, um die Nachricht festzulegen, die Sie anzeigen möchten. Weitere Informationen finden Sie unter [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Beispiel 3

In diesem Beispiel erstellen wir eine neue Richtlinie mit dem Namen off Shift Teams Access message1. In dieser Richtlinie wird die Verschiebungs basierte Anwesenheit aktiviert, und die folgende vordefinierte Meldung wird jedes Mal angezeigt, wenn ein Benutzer, dem diese Richtlinie zugewiesen ist, bei ausgeschalteter Schicht auf Teams zugreift.

  "Ihr Arbeitgeber genehmigt oder genehmigt die Nutzung seines Netzwerks, seiner Anwendungen, Systeme oder Tools nicht durch nicht freigestellte oder stündliche Mitarbeiter während der arbeitsfreien Stunden. Durch die Annahme erkennen Sie an, dass Ihre Nutzung von Teams während der Verlagerung nicht autorisiert ist und Sie nicht kompensiert werden. " 

Der Benutzer kann Teams verwenden, wenn die Umschaltfläche deaktiviert ist, wenn er die Nachricht akzeptiert, und die Nachfrist zwischen dem Beginn der ersten Schicht oder der letzten Schicht und dem Zeitpunkt, zu dem der Zugriff eingeschränkt ist, drei Minuten beträgt.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Verwenden Sie den **ShiftNoticeMessageType** -Parameter, um die Nachricht festzulegen, die Sie anzeigen möchten. Eine Liste der vordefinierten Nachrichten, die Sie für diesen Parameter auswählen können, finden Sie unter New-TeamsShiftPolicy.

### <a name="example-4"></a>Beispiel 4

In diesem Beispiel weisen wir eine Richtlinie mit dem Namen "aus Schicht Teams Zugriff benutzerdefinierter Nachricht" auf einen Benutzer mit dem Namen "Remy@contoso.com" zu.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der Schichten-App für Ihre Organisation in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](../../teams-powershell-overview.md)
