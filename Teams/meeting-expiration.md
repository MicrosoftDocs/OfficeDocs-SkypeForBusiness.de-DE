---
title: Besprechungsrichtlinien und Besprechungsablauf in Microsoft Teams
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
description: Erfahren Sie, wie Sie mithilfe von Besprechungsrichtlinieneinstellungen den Ablauf von Besprechungen in Microsoft Teams.
ms.openlocfilehash: e201348ba1734539844a76b0fee2e2f072757e87
ms.sourcegitcommit: 1c5608e6b539e90e42f48212d038f861ecf8136b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53337814"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Besprechungsrichtlinien und Besprechungsablauf in Microsoft Teams

[Besprechungsrichtlinien](meeting-policies-in-teams.md) in Microsoft Teams werden verwendet, um zu steuern, ob Benutzer in Ihrer Organisation Besprechungen starten und planen können, sowie die Features, die für Besprechungsteilnehmer für Besprechungen zur Verfügung stehen, die von Benutzern geplant werden. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sie verwalten Besprechungsrichtlinien im Microsoft Teams Admin Center oder mithilfe von [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell-Cmdlets.

Die Einstellungen der Besprechungsrichtlinie, die steuern, ob Benutzer Besprechungen starten und planen sowie den Ablauf von Besprechungen steuern können, die von Benutzern geplant werden. Wenn ein Teilnahmelink und eine Konferenz-ID für eine Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Die folgenden Einstellungen für Besprechungsrichtlinien bestimmen, ob Benutzer Besprechungen in einer Besprechung starten und Teams. Die Besprechungseinstellungen werden in diesem Artikel erläutert.

- [Jetzt besprechungen in Kanälen](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)zulassen: Steuert, ob ein Benutzer eine Besprechung aus dem Ausweg in einem Kanal starten kann.
- [Planen von Kanal-Besprechungen](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)zulassen: Steuert, ob ein Benutzer eine Besprechung in einem Kanal planen kann.
- [Planen privater Besprechungen](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)zulassen: Steuert, ob ein Benutzer eine private Besprechung in einem Teams. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Lassen Sie Outlook hinzufügen:](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)Steuert, ob ein Benutzer eine private Besprechung von einem anderen Outlook. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Sofortbesprechung in privaten Besprechungen](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)zulassen: Steuert, ob benutzerfreundliche private Besprechungen starten können.

Diese Einstellungen sind standardmäßig aktiviert. Wenn eine dieser Einstellungen deaktiviert ist, kann jeder Benutzer, dem die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen. Gleichzeitig treten der Besprechung Links und Konferenz-IDs aller vorhandenen Besprechungen des Typs bei, die der Benutzer zuvor begonnen oder geplant hat.

Wenn einem Benutzer beispielsweise eine Besprechungsrichtlinie zugewiesen ist, in der diese Einstellungen für die Besprechungsrichtlinie auf Ein festgelegt sind, und Sie dann die Einstellung Sofortbesprechung **in** Kanälen zulassen deaktivieren, kann dieser Benutzer keine Besprechungen in Kanälen aus dem Auslaufen mehr starten, und der Kanal "Jetzt beitreten"-Links, die der Benutzer zuvor erstellt hat, ist abgelaufen. Der Benutzer kann weiterhin andere Besprechungstypen starten und planen und an Besprechungen teilnehmen, die von anderen Personen organisiert werden.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Was geschieht, wenn der Teilnahmelink und die Konferenz-ID der Besprechung ablaufen?

Wenn der Teilnahmelink und die Konferenz-ID einer Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Wenn ein Benutzer versucht, über den Link oder per Telefon an der Besprechung zu teilnehmen, wird eine Meldung angezeigt, dass die Besprechung nicht mehr verfügbar ist. Unterhaltungen, Dateien, Whiteboards, Aufzeichnungen, Aufzeichnungen und andere mit der Besprechung zusammenhängende Inhalte bleiben erhalten, und die Benutzer können weiterhin darauf zugreifen.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Was geschieht, wenn Sie eine Besprechungsrichtlinieneinstellung aktivieren und deaktivieren?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Umschalten einer Besprechungsrichtlinieneinstellung von ein auf "aus"

Wenn eine Besprechungsrichtlinieneinstellung auf Ein festgelegt **ist,** können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen, und jeder kann teilnehmen. Wenn Sie die Einstellung für die Besprechungsrichtlinie auf Aus **festlegen,** können Benutzer, denen die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen, und die Besprechungslinks und Konferenz-IDs vorhandener Besprechungen, die der Benutzer zuvor geplant hat, laufen ab.

Denken Sie daran, dass der Benutzer weiterhin an Besprechungen teilnehmen kann, die von anderen Personen organisiert wurden.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Ändern der Einstellung für eine Besprechungsrichtlinie von "Ein" auf "Ein"

Wenn Sie eine Besprechungsrichtlinieneinstellung von **Aus** in **Ein** ändern, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen. Wenn eine Besprechungsrichtlinieneinstellung deaktiviert und dann für einen Benutzer erneut aktiviert ist, werden alle zuvor geplanten (und abgelaufenen) Besprechungen, die vom Benutzer organisiert wurden, aktiv, und personen können über den Teilnahmelink oder per Telefon an der Besprechung teilnehmen.  

## <a name="meeting-expiration-scenarios"></a>Szenarien für den Ablauf von Besprechungen

Hier ist eine Zusammenfassung der Funktionsweise des Ablaufs von Besprechungen für jede der in diesem Artikel erläuterten Besprechungsrichtlinieneinstellungen.

|Sie möchten...&nbsp;&nbsp; |So geht's&nbsp;&nbsp;&nbsp;&nbsp;  |Besprechungs-Joinverhalten&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Ablaufen von privaten "Jetzt treffen"-Besprechungen, die von einem Benutzer gestartet wurden&nbsp;&nbsp;|Deaktivieren Sie **"Sofortbesprechung in privaten Besprechungen zulassen"**.&nbsp;&nbsp;|Niemand kann an privaten **Besprechungen teilnehmen, die** vom Benutzer gestartet wurden.|
|Ablauf von privaten Besprechungen, die von einem Benutzer geplant wurden&nbsp;&nbsp;|Deaktivieren Sie **Die Planung privater Besprechungen zulassen,**  und deaktivieren Sie **Outlook-Add-In zulassen.** &nbsp;&nbsp;|Niemand kann an privaten, vom Benutzer geplanten Besprechungen teilnehmen. Dadurch wird verhindert, dass Personen an folgenden Besprechungen teilnehmen:<ul><li>Private Besprechungen, die in der Vergangenheit stattgefunden haben.</li><li>Private Besprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von besprechungsserien privaten Besprechungen.</li></ul><br>Sowohl **Das Planen privater Besprechungen** zulassen als auch das **Add-Outlook-Add-Ins** muss deaktiviert sein, damit private, von einem Benutzer geplante Besprechungen ablaufen. Wenn eine Einstellung deaktiviert und die andere aktiviert ist, bleiben Besprechungslinks und Konferenz-IDs vorhandener Besprechungen aktiv und laufen nicht ab.|
|Kanal läuft ab **Besprechungen jetzt** beginnen von einem Benutzer&nbsp;&nbsp;|Deaktivieren Sie **"Sofort besprechung in Kanälen zulassen"** _und_ deaktivieren Sie **Kanal-Besprechungsplanung zulassen.**&nbsp;&nbsp;|Niemand kann an **Kanalbesprechungen teilnehmen, die** vom Benutzer gestartet wurden.|
|Ablaufen von Kanalbesprechungen, die von einem Benutzer geplant wurden&nbsp;&nbsp;|Deaktivieren Sie **Kanal-Besprechungsplanung zulassen.**&nbsp;&nbsp;|Niemand kann an Kanalbesprechungen teilnehmen, die vom Benutzer geplant wurden. Dadurch wird verhindert, dass Personen an folgenden Besprechungen teilnehmen:<ul><li>Kanalbesprechungen, die in der Vergangenheit stattgefunden haben.</li><li>Kanalbesprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von Besprechungsserien in Kanälen.</li></ul>|

Wenn Sie Personen Den Zugriff auf Besprechungen wünschen, die zuvor von einem bestimmten Benutzer geplant oder gestartet wurden, können Sie:

- Aktivieren Sie die Besprechungsrichtlinieneinstellung für den Benutzer.
- Deaktivieren Sie die Besprechungsrichtlinieneinstellung für den Benutzer, und lassen Sie einen anderen Benutzer, für den die Richtlinieneinstellung aktiviert ist, eine neue Besprechung erstellen, um die abgelaufene Besprechung zu ersetzen.

> [!NOTE]
> Wenn die Besprechung von einer Stellvertretung gesendet wurde, der die Berechtigung zum Senden von Besprechungseinladungen im Auftrag einer anderen Person, z. B. eines Vorgesetzten, erteilt wurde, wird die Einstellung der Besprechungsrichtlinie auf die Person angewendet, die die Berechtigung erteilt hat (der Vorgesetzte).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
