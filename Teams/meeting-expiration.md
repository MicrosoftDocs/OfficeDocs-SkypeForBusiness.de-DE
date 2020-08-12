---
title: Besprechungsrichtlinien und Ablauf der Besprechung in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Erfahren Sie, wie Sie mithilfe von Besprechungsrichtlinien Einstellungen das Ablaufdatum von Besprechungen in Microsoft Teams steuern können.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e25ea1c55890a78e9e492dd2c2dd419a6ed34f2
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640982"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Besprechungsrichtlinien und Ablauf der Besprechung in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Übersicht

[Besprechungsrichtlinien](meeting-policies-in-teams.md) in Microsoft Teams werden verwendet, um zu steuern, ob Benutzer in Ihrer Organisation Besprechungen starten und planen können, sowie die Features, die Besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern geplant werden. Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sie verwalten Besprechungsrichtlinien im Microsoft Teams Admin Center oder mithilfe von [Get](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy), [New](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy), [Sets](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell-Cmdlets.

Die Besprechungsrichtlinien Einstellungen, die Steuern, ob Benutzer Besprechungen starten und planen können, Steuern auch das Ablaufen von Besprechungen, die von Benutzern geplant werden. Wenn ein Link für die Besprechungsteilnahme und die Konferenz-ID für eine Besprechung ablaufen, kann niemand an der Besprechung teilnehmen. Die folgenden Besprechungsrichtlinien Einstellungen legen fest, ob Benutzer Besprechungen in Teams starten und planen können, und wir verweisen in diesem Artikel auf Sie.

- [Sofortbesprechung in Kanälen zulassen](meeting-policies-in-teams.md#allow-meet-now-in-channels): steuert, ob ein Benutzer eine spontane Besprechung in einem Kanal starten kann.
- [Kanal-Besprechungsplanung zulassen](meeting-policies-in-teams.md#allow-channel-meeting-scheduling): steuert, ob ein Benutzer eine Besprechung in einem Kanal planen kann.
- [Planen privater Besprechungen zulassen](meeting-policies-in-teams.md#allow-scheduling-private-meetings): steuert, ob ein Benutzer eine private Besprechung in Teams planen kann. Eine Besprechung ist privat, wenn Sie nicht in einem Kanal in einem Team veröffentlicht wurde.
- [Outlook-Add in zulassen](meeting-policies-in-teams.md#allow-the-outlook-add-in): steuert, ob ein Benutzer eine private Besprechung in Outlook planen kann. Eine Besprechung ist privat, wenn Sie nicht in einem Kanal in einem Team veröffentlicht wurde.
- "Besprechung [jetzt in privaten Besprechungen zulassen](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)": steuert, ob ein Benutzer eine spontane private Besprechung starten kann.

Diese Einstellungen sind standardmäßig aktiviert. Wenn eine dieser Einstellungen deaktiviert ist, können alle Benutzer, denen die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen. Gleichzeitig verfallen die Besprechungs Verknüpfungen und Konferenz-IDs aller vorhandenen Besprechungen dieses Typs, die der Benutzer zuvor gestartet oder geplant abläuft.

Wenn einem Benutzer beispielsweise eine Besprechungsrichtlinie zugewiesen ist, in der diese Besprechungsrichtlinien Einstellungen auf ein festgelegt **sind, und**Sie dann die Einstellung " **jetzt in Kanälen zulassen** " deaktivieren, kann dieser Benutzer keine spontanen Besprechungen mehr in Kanälen starten, und der Kanal erfüllt nun Join-Links, die der zuvor erstellte Benutzer abgelaufen ist. Der Benutzer kann weiterhin andere Besprechungstypen starten und planen und an Besprechungen teilnehmen, die von anderen Personen organisiert werden.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Was geschieht, wenn der Link zur Besprechungsteilnahme und die Konferenz-ID ablaufen?

Wenn der Link für die Besprechungsteilnahme und die Konferenz-ID für eine Besprechung ablaufen, kann niemand an der Besprechung teilnehmen. Wenn ein Benutzer versucht, über den Link oder per Telefon an der Besprechung teilzunehmen, wird eine Meldung angezeigt, die besagt, dass die Besprechung nicht mehr verfügbar ist. Unterhaltungen, Dateien, Whiteboards, Aufzeichnungen, Transkripte und andere Inhalte, die sich auf die Besprechung beziehen, werden beibehalten, und Benutzer können weiterhin darauf zugreifen.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Was geschieht, wenn Sie eine Besprechungsrichtlinien Einstellung aktivieren und deaktivieren?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Umschalten einer Besprechungsrichtlinien Einstellung von ein auf aus

Wenn eine Besprechungsrichtlinien Einstellung **auf**"ein" festgelegt ist, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen, und jeder kann teilnehmen. Wenn Sie die Einstellung für die Besprechungsrichtlinie auf **aus**umschalten, können Benutzer, denen die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen, und die Besprechungs Verknüpfungs-und Konferenz-IDs vorhandener Besprechungen, die der Benutzer zuvor geplant hat, sind abgelaufen.

Beachten Sie, dass der Benutzer weiterhin an Besprechungen teilnehmen kann, die von anderen Personen organisiert werden.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Umschalten einer Besprechungsrichtlinien Einstellung von "aus" auf "ein"

Wenn Sie eine Besprechungsrichtlinien **Einstellung von aus auf** ein **umschalten, können Benutzer, denen**die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen. Wenn eine Einstellung für eine Besprechungsrichtlinie deaktiviert und dann wieder für einen Benutzer aktiviert ist, werden alle zuvor geplanten (und abgelaufenen) Besprechungen, die vom Benutzer organisiert wurden, aktiv, und Personen können mit dem Link für die Besprechungsteilnahme oder per Telefon teilnehmen.  

## <a name="meeting-expiration-scenarios"></a>Ablaufszenarien für Besprechungen

Nachfolgend finden Sie eine Zusammenfassung der Funktionsweise des Ablaufs von Besprechungen für jede der in diesem Artikel behandelten Besprechungsrichtlinien Einstellungen. 

|Wenn Sie möchten... |Vorgehensweise  |Verhalten der Besprechungsteilnahme  |
|---------|---------|---------|
|Ablaufkanal ablaufen, Besprechungen, die von einem Benutzer gestartet wurden  |Deaktivieren Sie die Option "jetzt besprechen" **in den Kanälen**.|Niemand kann an Channel teilnehmen, jetzt treffen, die vom Benutzer gestartet wurden         |
|Ablauf von Kanal Besprechungen, die von einem Benutzer geplant werden   |Deaktivieren Sie die Option **Kanal Besprechung planen zulassen**.         |Niemand kann an Kanal Besprechungen teilnehmen, die vom Benutzer geplant wurden. Dadurch wird verhindert, dass Personen an folgendem teilnehmen:<ul><li>Kanal Besprechungen, die in der Vergangenheit stattgefunden haben.</li> <li>Kanal Besprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von wiederkehrenden Kanal Besprechungen</li></ul>       |
|Ablaufen privater Besprechungen, die von einem Benutzer geplant werden    |Deaktivieren Sie die Option **Planen privater Besprechungen zulassen** *, und* deaktivieren Sie **das Outlook-Add-in zulassen**.          |Niemand kann an privaten Besprechungen teilnehmen, die vom Benutzer geplant wurden. Dadurch wird verhindert, dass Personen an folgendem teilnehmen: <ul><li>Private Besprechungen, die in der Vergangenheit aufgetreten sind.</li> <li>Private Besprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von wiederkehrenden privaten Besprechungen</li></ul> Sowohl das **Planen privater Besprechungen** als auch **das zulassen, dass das Outlook-Add-in** deaktiviert ist, um private Besprechungen zu verfallen, die von einem Benutzer geplant wurden. Wenn eine Einstellung deaktiviert und die andere aktiviert ist, bleiben Besprechungs Verknüpfungs Verknüpfungen und Konferenz-IDs vorhandener Besprechungen aktiv und sind nicht abgelaufen.      |
|Ablaufen privater Besprechungen, die von einem Benutzer gestartet wurden  |Deaktivieren Sie die Option " **Besprechung jetzt in privaten Besprechungen zulassen**".          |Niemand kann an privaten Besprechungen teilnehmen, die vom Benutzer gestartet wurden.         |

Wenn Sie möchten, dass Personen auf Besprechungen zugreifen können, die zuvor von einem bestimmten Benutzer geplant oder gestartet wurden, haben Sie folgende Möglichkeiten:

- Aktivieren Sie die Besprechungsrichtlinien Einstellung für diesen Benutzer.
- Deaktivieren Sie die Einstellung der Besprechungsrichtlinie für diesen Benutzer, und weisen Sie einen anderen Benutzer auf, für den die Richtlinieneinstellung aktiviert ist, erstellen Sie eine neue Besprechung, um die abgelaufene Besprechung zu ersetzen.

> [!NOTE]
> Wenn die Besprechung von einer Stellvertretung gesendet wurde, der die Berechtigung zum Senden von Besprechungseinladungen im Namen einer anderen Person wie einem Manager gewährt wurde, wird die Einstellung für die Besprechungsrichtlinie auf die Person angewendet, die die Berechtigung erteilt hat (der Manager).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)