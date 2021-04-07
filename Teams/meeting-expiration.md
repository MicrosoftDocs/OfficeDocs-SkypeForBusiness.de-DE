---
title: Besprechungsrichtlinien und Ablauf der Besprechung in Microsoft Teams
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
description: Erfahren Sie, wie Sie die Besprechungsrichtlinieneinstellungen verwenden, um den Ablauf von Besprechungen in Microsoft Teams zu steuern.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6e8821781eab70696c9b24c8df18cc8dd0b46870
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598614"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Besprechungsrichtlinien und Ablauf der Besprechung in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Übersicht

[Besprechungsrichtlinien](meeting-policies-in-teams.md) in Microsoft Teams werden verwendet, um zu steuern, ob Benutzer in Ihrer Organisation Besprechungen starten und planen können, sowie die Features, die besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern geplant werden. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sie verwalten Besprechungsrichtlinien im Microsoft Teams Admin Center oder verwenden [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell-Cmdlets.

Die Besprechungsrichtlinieneinstellungen, die steuern, ob Benutzer Besprechungen starten und planen können, steuern auch den Ablauf von Besprechungen, die von Benutzern geplant wurden. Wenn ein Link für die Teilnahme an einer Besprechung und die Konferenz-ID für eine Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Die folgenden Besprechungsrichtlinieneinstellungen bestimmen, ob Benutzer Besprechungen in Teams starten und planen können, und wir beziehen uns in diesem Artikel auf sie.

- [Jetzt in Kanälen](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)besprechung zulassen: Steuert, ob ein Benutzer eine sofort anmutende Besprechung in einem Kanal starten kann.
- [Kanalplanung zulassen:](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)Steuert, ob ein Benutzer eine Besprechung in einem Kanal planen kann.
- [Planen privater Besprechungen](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)zulassen: Steuert, ob ein Benutzer eine private Besprechung in Teams planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Zulassen des Outlook-Add-Ins:](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)Steuert, ob ein Benutzer eine private Besprechung in Outlook planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Besprechung jetzt in privaten Besprechungen](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)zulassen: Steuert, ob ein Benutzer eine sofort anberaumte private Besprechung starten kann.

Standardmäßig sind diese Einstellungen aktiviert. Wenn eine dieser Einstellungen deaktiviert ist, kann jeder Benutzer, dem die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen. Gleichzeitig nehmen die Besprechung an Links und Konferenz-IDs aller vorhandenen Besprechungen dieses Typs teil, die der Benutzer zuvor gestartet oder geplant hat.

Wenn einem Benutzer z. B. eine Besprechungsrichtlinie zugewiesen ist, in der diese Besprechungsrichtlinieneinstellungen auf **Ein** festgelegt sind und Sie dann die Einstellung Besprechung jetzt **in** Kanälen zulassen deaktivieren, kann dieser Benutzer keine Sofortbesprechungen mehr in Kanälen starten, und der Kanal "Jetzt teilnehmen"-Verknüpfungen, die der Benutzer zuvor erstellt hat, ist abgelaufen. Der Benutzer kann weiterhin andere Besprechungstypen starten und planen und an Besprechungen teilnehmen, die von anderen Personen organisiert werden.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Was geschieht, wenn der Link zur Besprechungs-Teilnahme und die Konferenz-ID ablaufen?

Wenn der Link für die Besprechungs-Teilnahme und die Konferenz-ID für eine Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Wenn ein Benutzer versucht, über den Link oder per Telefon an der Besprechung teil zu nehmen, wird eine Meldung angezeigt, dass die Besprechung nicht mehr verfügbar ist. Unterhaltungen, Dateien, Whiteboards, Aufzeichnungen, Transkripte und andere Inhalte im Zusammenhang mit der Besprechung bleiben erhalten, und die Benutzer können weiterhin darauf zugreifen.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Was geschieht, wenn Sie eine Besprechungsrichtlinieneinstellung aktivieren und deaktivieren?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Umschalten einer Besprechungsrichtlinieneinstellung von ein auf eins

Wenn eine Besprechungsrichtlinieneinstellung auf **Ein** festgelegt ist, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen, und jeder kann teilnehmen. Wenn Sie die Einstellung für Besprechungsrichtlinien auf **Aus** umschalten, können Benutzer, denen die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen, und die Besprechungslinks und Konferenz-IDs vorhandener Besprechungen, die der Benutzer zuvor geplant hat, sind abgelaufen.

Denken Sie daran, dass der Benutzer weiterhin an Besprechungen teilnehmen kann, die von anderen Personen organisiert wurden.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Umschalten einer Besprechungsrichtlinieneinstellung von aus auf ein

Wenn Sie eine Besprechungsrichtlinieneinstellung von **Aus** auf **Ein** umschalten, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen. Wenn eine Einstellung für besprechungsrichtlinien für einen Benutzer deaktiviert und dann erneut aktiviert ist, werden alle zuvor geplanten (und abgelaufenen) Besprechungen, die vom Benutzer organisiert wurden, aktiv, und die Personen können über den Link für die Teilnahme an der Besprechung oder per Telefon teilnehmen.  

## <a name="meeting-expiration-scenarios"></a>Ablaufszenarien für Besprechungen

Hier finden Sie eine Zusammenfassung der Funktionsweise des Ablaufs der Besprechung für jede der in diesem Artikel erläuterten Besprechungsrichtlinieneinstellungen. 

|Sie möchten ... |Gehen Sie dazu vor  |Verhalten der Besprechungs teilnehmen  |
|---------|---------|---------|
|Ablaufkanal Besprechungen, die von einem Benutzer gestartet wurden  |Deaktivieren Sie **"Jetzt treffen zulassen" in Kanälen.**|Niemand kann am Kanal Besprechungen jetzt teilnehmen, die vom Benutzer gestartet wurden.         |
|Ablaufen von Kanalbesprechungen, die von einem Benutzer geplant wurden   |Deaktivieren Sie **Kanal-Besprechungsplanung zulassen.**         |Niemand kann an vom Benutzer geplanten Kanalbesprechungen teilnehmen. Dadurch wird verhindert, dass Personen den folgenden Personen beitreten:<ul><li>Kanalbesprechungen, die in der Vergangenheit stattgefunden haben.</li> <li>Kanalbesprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen wiederkehrender Kanalbesprechungen.</li></ul>       |
|Ablaufen privater Besprechungen, die von einem Benutzer geplant wurden    |Deaktivieren Sie **Die Planung privater Besprechungen zulassen** *und* **das Outlook-Add-In zulassen.**          |Niemand kann an privaten, vom Benutzer geplanten Besprechungen teilnehmen. Dadurch wird verhindert, dass Personen den folgenden Personen beitreten: <ul><li>Private Besprechungen, die in der Vergangenheit stattgefunden haben.</li> <li>Private Besprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen wiederkehrender privater Besprechungen.</li></ul> Sowohl **Das Planen privater Besprechungen** zulassen als auch das **Outlook-Add-In** zulassen müssen deaktiviert sein, um private Besprechungen abläuft, die von einem Benutzer geplant wurden. Wenn eine Einstellung deaktiviert und die andere aktiviert ist, bleiben Verknüpfungen und Konferenz-IDs vorhandener Besprechungen aktiv und laufen nicht ab.      |
|Ablaufen privater Besprechungen, die von einem Benutzer gestartet wurden  |Deaktivieren Sie **"Besprechung jetzt zulassen" in privaten Besprechungen.**          |Niemand kann an privaten Besprechungen teilnehmen, die vom Benutzer gestartet wurden.         |

Wenn Sie möchten, dass Personen auf Besprechungen zugreifen, die zuvor von einem bestimmten Benutzer geplant oder gestartet wurden, können Sie:

- Aktivieren Sie die Besprechungsrichtlinieneinstellung für den Benutzer.
- Deaktivieren Sie die Besprechungsrichtlinieneinstellung für den Benutzer, und lassen Sie einen anderen Benutzer, für den die Richtlinieneinstellung aktiviert ist, eine neue Besprechung erstellen, um die abgelaufene Besprechung zu ersetzen.

> [!NOTE]
> Wenn die Besprechung von einer Stellvertretung gesendet wurde, der die Berechtigung zum Senden von Besprechungseinladungen im Auftrag einer anderen Person, z. B. eines Vorgesetzten, erteilt wurde, wird die Besprechungsrichtlinieneinstellung auf die Person angewendet, die die Berechtigung erteilt hat (der Vorgesetzte).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)