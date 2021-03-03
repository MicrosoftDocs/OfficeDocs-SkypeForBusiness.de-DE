---
title: Besprechungsrichtlinien und Ablauf von Besprechungen in Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Erfahren Sie, wie Sie mithilfe von Besprechungsrichtlinieneinstellungen den Ablauf von Besprechungen in Microsoft Teams steuern.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e1efb8ac21cbe669bcea3569a5e231469685a249
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827525"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Besprechungsrichtlinien und Ablauf von Besprechungen in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Übersicht

[Besprechungsrichtlinien](meeting-policies-in-teams.md) in Microsoft Teams werden verwendet, um zu steuern, ob Benutzer in Ihrer Organisation Besprechungen starten und planen können, sowie die Features, die für Besprechungsteilnehmer für Besprechungen zur Verfügung stehen, die von Benutzern geplant werden. Sie können die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sie verwalten Besprechungsrichtlinien im Microsoft Teams Admin [](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)Center oder verwenden die PowerShell-Cmdlets ["Get",](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy)"New", ["Set",](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) ["Remove"](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy)und ["Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy".

Die Besprechungsrichtlinieneinstellungen, die steuern, ob Benutzer Besprechungen starten und planen können, steuern auch den Ablauf von Besprechungen, die von Benutzern geplant wurden. Wenn ein Link zur Teilnahme an einer Besprechung und die Konferenz-ID für eine Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Die folgenden Einstellungen für Besprechungsrichtlinien bestimmen, ob Benutzer Besprechungen in Teams starten und planen können, und wir beziehen uns in diesem Artikel auf sie.

- ["Jetzt in Kanälen besprechungen zulassen":](meeting-policies-in-teams.md#allow-meet-now-in-channels)Steuert, ob ein Benutzer eine Besprechung ohne Umweg in einem Kanal starten kann.
- [Planen von Kanal-Besprechungen](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)zulassen: Steuert, ob ein Benutzer eine Besprechung in einem Kanal planen kann.
- [Planen privater Besprechungen zulassen:](meeting-policies-in-teams.md#allow-scheduling-private-meetings)Steuert, ob ein Benutzer eine private Besprechung in Teams planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Outlook-Add-In](meeting-policies-in-teams.md#allow-the-outlook-add-in)zulassen: Steuert, ob ein Benutzer eine private Besprechung in Outlook planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- ["Sofortbesprechung in privaten Besprechungen zulassen":](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)Steuert, ob ein Benutzer eine zusätzliche private Besprechung starten kann.

Diese Einstellungen sind standardmäßig aktiviert. Wenn eine dieser Einstellungen deaktiviert ist, kann jeder Benutzer, dem die Richtlinie zugewiesen ist, besprechungen dieses Typs nicht starten oder neue Besprechungen planen. Gleichzeitig treten die Besprechungslinks und Konferenz-IDs aller vorhandenen Besprechungen dieses Typs, die der Benutzer zuvor gestartet oder geplant hat, ab.

Wenn einem Benutzer beispielsweise eine Besprechungsrichtlinie zugewiesen ist, in der diese Besprechungsrichtlinieneinstellungen auf **"Ein"** festgelegt sind, und Sie dann die Einstellung "Sofortbesprechung **in** Kanälen zulassen" deaktivieren, kann dieser Benutzer keine auslaufende Besprechung mehr in Kanälen starten, und der Kanal "Jetzt beitreten"-Links, die der Benutzer zuvor erstellt hat, ist abgelaufen. Der Benutzer kann weiterhin andere Besprechungstypen starten und planen und an Besprechungen teilnehmen, die von anderen Personen organisiert werden.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Was geschieht, wenn der Teilnahmelink und die Konferenz-ID ablaufen?

Wenn der Besprechungslink und die Konferenz-ID für eine Besprechung ablaufen, kann niemand an der Besprechung teilnehmen. Wenn ein Benutzer versucht, über den Link oder per Telefon an der Besprechung zu teilnehmen, wird eine Meldung angezeigt, dass die Besprechung nicht mehr verfügbar ist. Unterhaltungen, Dateien, Whiteboards, Aufzeichnungen, Transkription und andere Inhalte im Zusammenhang mit der Besprechung bleiben erhalten, und die Benutzer können weiterhin darauf zugreifen.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Was geschieht, wenn Sie eine Besprechungsrichtlinieneinstellung aktivieren und deaktivieren?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Umschalten einer Besprechungsrichtlinieneinstellung von ein auf eins

Wenn eine Besprechungsrichtlinieneinstellung auf **"Ein"** festgelegt ist, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen, und jeder kann teilnehmen. Wenn Sie die Einstellung für die Besprechungsrichtlinie auf "Aus" **festlegen,** können Benutzer, denen die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen, und die Besprechungslinks und Konferenz-IDs vorhandener Besprechungen, die der Benutzer zuvor geplant hat, laufen ab.

Denken Sie daran, dass der Benutzer dennoch an Besprechungen teilnehmen kann, die von anderen Personen organisiert wurden.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Umschalten einer Besprechungsrichtlinieneinstellung von "Ein" auf "Ein"

Wenn Sie eine Besprechungsrichtlinieneinstellung von **"Aus"** in **"Ein"** ändern, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen. Wenn eine Besprechungsrichtlinieneinstellung für einen Benutzer deaktiviert und dann wieder aktiviert ist, werden alle zuvor vom Benutzer organisierten (und abgelaufenen) Besprechungen aktiv, und die Personen können über den Teilnahmelink oder per Telefon an der Besprechung teilnehmen.  

## <a name="meeting-expiration-scenarios"></a>Besprechungsablaufszenarien

Hier ist eine Zusammenfassung der Funktionsweise des Ablaufs von Besprechungen für jede der in diesem Artikel erläuterten Besprechungsrichtlinieneinstellungen. 

|Sie möchten ... |So geht's  |Besprechungs-Join-Verhalten  |
|---------|---------|---------|
|Ablaufen von Kanalbesprechungen, die von einem Benutzer gestartet wurden  |Deaktivieren Sie **"Soforttreffen in Kanälen zulassen".**|Niemand kann an Kanalbesprechungen teilnehmen, die vom Benutzer gestartet wurden.         |
|Ablaufen von Kanalbesprechungen, die von einem Benutzer geplant wurden   |Deaktivieren Sie **"Kanal-Besprechungsplanung zulassen".**         |Niemand kann an vom Benutzer geplanten Kanalbesprechungen teilnehmen. Dadurch wird verhindert, dass Benutzer den folgenden Aufgaben beitreten:<ul><li>Kanalbesprechungen, die in der Vergangenheit stattgefunden haben.</li> <li>Kanalbesprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von Kanalbesprechungen.</li></ul>       |
|Ablauf von privaten Besprechungen, die von einem Benutzer geplant wurden    |Deaktivieren Sie **"Planen privater Besprechungen zulassen"** *und* deaktivieren Sie **"Outlook-Add-In zulassen".**          |Niemand kann an privaten, vom Benutzer geplanten Besprechungen teilnehmen. Dadurch wird verhindert, dass Benutzer den folgenden Aufgaben beitreten: <ul><li>Private Besprechungen, die in der Vergangenheit stattgefunden haben.</li> <li>Private Besprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von privaten Besprechungsserien.</li></ul> Sowohl **das Planen privater Besprechungen** zulassen als auch das **Outlook-Add-In** zulassen müssen deaktiviert sein, um private, von einem Benutzer geplante Besprechungen zu ablaufen. Wenn eine Einstellung deaktiviert und die andere aktiviert ist, bleiben besprechungsteilmachende Links und Konferenz-IDs vorhandener Besprechungen aktiv und laufen nicht ab.      |
|Ablaufen privater Besprechungen, die von einem Benutzer gestartet wurden  |Deaktivieren Sie **"Sofortbesprechung in privaten Besprechungen zulassen".**          |Niemand kann an privaten Besprechungen teilnehmen, die vom Benutzer gestartet wurden.         |

Wenn Sie möchten, dass Personen auf Besprechungen zugreifen können, die zuvor von einem bestimmten Benutzer geplant oder gestartet wurden, haben Sie dies:

- Aktivieren Sie die Besprechungsrichtlinieneinstellung für den Benutzer.
- Deaktivieren Sie die Besprechungsrichtlinieneinstellung für den Benutzer, und lassen Sie einen anderen Benutzer, für den die Richtlinieneinstellung aktiviert ist, eine neue Besprechung erstellen, um die abgelaufene Besprechung zu ersetzen.

> [!NOTE]
> Wenn die Besprechung von einer Stellvertretung gesendet wurde, der die Berechtigung zum Senden von Besprechungseinladungen im Auftrag einer anderen Person, z. B. eines Vorgesetzten, erteilt wurde, wird die Besprechungsrichtlinieneinstellung auf die Person angewendet, die die Berechtigung erteilt hat (der Vorgesetzte).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Besprechungsrichtlinien in Microsoft Teams](meeting-policies-in-teams.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)