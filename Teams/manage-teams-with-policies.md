---
title: Verwalten von Teams mit Richtlinien
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Lehnen Sie sich an Teams-Richtlinien an.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f06e9aa87cc0c1af758bf0c8c9abad6641debbd
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460495"
---
# <a name="manage-teams-with-policies"></a>Verwalten von Teams mit Richtlinien

Richtlinien sind ein wichtiger Bestandteil der Verwaltung von Teams. In diesem Artikel können Sie navigieren, wie Richtlinien zum Nutzen Ihrer Organisation verwendet werden.

## <a name="what-you-use-policies-for"></a>Verwenden von Richtlinien für

Richtlinien werden verwendet, um viele Aufgaben in Ihrer Organisation in verschiedenen Bereichen wie Messaging, Besprechungen und Anwendungen auszuführen. Einige der Dinge, die Sie tun können, umfassen das Planen von Besprechungen in einem Teamkanal, das Bearbeiten gesendeter Nachrichten durch Benutzer und das Steuern, ob Benutzer Apps an die Teams-App-Leiste anheften können.

## <a name="how-to-assign-policies"></a>Zuweisen von Richtlinien

Richtlinien können auf verschiedene Arten zugewiesen werden, je nachdem, was Ihre Organisation zu erreichen versucht. Sie können Aufgaben im Teams Admin Center erstellen und anzeigen.

![Screenshot der Gruppenrichtlinienzuordnung.](media/group-policy-assignment.png)

Weitere Informationen zum Zuweisen von Richtlinien finden Sie [hier.](assign-policies.md)

## <a name="how-to-manage-policies"></a>Verwalten von Richtlinien

Richtlinien werden mit dem Microsoft Teams Admin Center oder [mit PowerShell verwaltet.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)

Mit einer App-Setuprichtlinie können Sie beispielsweise Benutzern das Hochladen benutzerdefinierter Apps, das Installieren von Apps im Auftrag Ihrer Benutzer und das Anheften von Apps an die Teams-App-Leiste ermöglichen. Diese Richtlinien werden im Teams Admin Center konfiguriert.

![Screenshot der App-Setuprichtlinie.](media/app-setup-policy.png)

Darüber hinaus kann eine Besprechungsrichtlinie verwendet werden, um Audio- und Videoeinstellungen in Teams-Besprechungen wie Transkriptionen, Cloudaufzeichnungen und IP-Audio/Video zu steuern.

![Screenshot der Besprechungsrichtlinie.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Microsoft Teams für Bildungseinrichtungen

Sie können auch den [Richtlinien-Assistenten für Teams for Education](easy-policy-setup-edu.md) verwenden, um Richtlinien für Ihre Lernumgebung auf einfache Weise zu erstellen und zu verwalten.

![Screenshot des Richtlinien-Assistenten für Teams for Education.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Richtlinientypen

Die folgenden Richtlinien können mit Microsoft Teams verwaltet werden.

Richtlinientyp | Beschreibung
------------|------------
[Richtlinienpakete](manage-policy-packages.md) | Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Einstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben.
[Besprechungsrichtlinien](meeting-policies-in-teams.md) | Eine Besprechungsrichtlinie wird verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern in Ihrer Organisation geplant wurden. Besprechungsrichtlinien umfassen die folgenden Themen.<br> - Audio- und Videorichtlinien<br> - Richtlinien für Inhalts- und Bildschirmfreigabe<br> – Teilnehmer-, Gäste- und Zugriffsrichtlinien<br> – Allgemeine Richtlinien
[Sprach- und Anrufrichtlinien](voice-and-calling-policies.md)| Sprach- und Anrufrichtlinien verwalten diese Einstellungen über Teams wie Notrufe, Anrufrouting und Anrufer-ID.
[App-Richtlinien](app-policies.md)| App-Richtlinien werden zum Steuern von Anwendungen in Microsoft Teams verwendet. Administratoren können zulassen oder blockieren, welche Apps Benutzer installieren können, Anwendungen an die Teams-App-Leiste eines Benutzers anheften und die Anwendung im Auftrag Ihrer Benutzer installieren.
[Messagingrichtlinien](messaging-policies-in-teams.md)| Messagingrichtlinien steuern die Verfügbarkeit von Chat- und Kanalfeatures.

## <a name="related-topics"></a>Verwandte Themen

* [Verwalten von Feedbackrichtlinien in Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Verwalten von Teamrichtlinien in Microsoft Teams](teams-policies.md)
* [Anzeigen von Richtlinienzuordnungen im Aktivitätsprotokoll](activity-log.md)
* [Einrichten von Live-Ereignissen in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Richtlinien und Richtlinienpakete für Teams für Bildungseinrichtungen](policy-packages-edu.md)
