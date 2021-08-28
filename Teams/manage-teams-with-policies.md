---
title: Verwalten Teams mit Richtlinien
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informationen zu Teams Richtlinien.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 307eccf1d6e919593cdfadaf2b902a7a15c7b4cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588147"
---
# <a name="manage-teams-with-policies"></a>Verwalten Teams mit Richtlinien

Richtlinien sind ein wichtiger Bestandteil der Verwaltung Teams. In diesem Artikel erfahren Sie, wie Richtlinien zum Nutzen Ihrer Organisation verwendet werden.

## <a name="what-you-use-policies-for"></a>Für was Sie Richtlinien verwenden

Richtlinien werden verwendet, um viele Aufgaben in Ihrer Organisation in verschiedenen Bereichen, z. B. Nachrichten, Besprechungen und Anwendungen, auszuführen. Zu den Dingen, die Sie tun können, gehören das Planen von Besprechungen in einem Teams-Kanal, das Ermöglichen der Bearbeitung gesendeter Nachrichten durch Benutzer und das Steuern, ob Benutzer Apps an die App-Leiste Teams können.

## <a name="how-to-assign-policies"></a>Zuweisen von Richtlinien

Richtlinien können auf verschiedene Arten zugewiesen werden, je nachdem, was Ihre Organisation zu erreichen versucht. Sie können Aufgaben im Admin Center Teams anzeigen.

![Screenshot der Gruppenrichtlinienzuweisung](media/group-policy-assignment.png)

Weitere Informationen zum Zuweisen von Richtlinien finden [Sie hier.](policy-assignment-overview.md)

## <a name="how-to-manage-policies"></a>So wird's geschafft: Verwalten von Richtlinien

Richtlinien werden mit dem Microsoft Teams Admin Center oder [mithilfe von PowerShell verwaltet.](./teams-powershell-managing-teams.md#manage-policies-via-powershell)

Eine App-Setuprichtlinie kann es Ihnen z. B. ermöglichen, Benutzern das Hochladen benutzerdefinierter Apps, das Installieren von Apps im Auftrag Ihrer Benutzer und das Anheften von Apps an die Teams App-Leiste zu ermöglichen. Diese Richtlinien werden im Teams Admin Center konfiguriert.

![Screenshot der App-Setuprichtlinie.](media/app-setup-policy.png)

Darüber hinaus kann eine Besprechungsrichtlinie verwendet werden, um Audio- und Videoeinstellungen in Teams-Besprechungen wie Transkriptionen, Cloudaufzeichnungen und IP-Audio/-Video zu steuern.

![Screenshot der Besprechungsrichtlinie.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Microsoft Teams für Bildungseinrichtungen

Sie können auch den Assistenten für [Teams für Education-Richtlinien](easy-policy-setup-edu.md) verwenden, um Richtlinien für Ihre Lernumgebung auf einfache Weise zu erstellen und zu verwalten.

![Screenshot des Teams für Education-Richtlinien-Assistenten](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Richtlinientypen

Die folgenden Richtlinien können mit einem Konto verwaltet Microsoft Teams.

Richtlinientyp | Beschreibung
------------|------------
[Richtlinienpakete](manage-policy-packages.md) | Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Einstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben.
[Besprechungsrichtlinien](meeting-policies-in-teams.md) | Eine Besprechungsrichtlinie wird verwendet, um die Features zu steuern, die für Besprechungsteilnehmer für Besprechungen zur Verfügung stehen, die von Benutzern in Ihrer Organisation geplant wurden. Zu den Besprechungsrichtlinien gehören die folgenden Themen:<br> - Richtlinien für Audio und Video<br> - Richtlinien für die Inhalts- und Bildschirmfreigabe<br> – Teilnehmer-, Gäste- und Zugriffsrichtlinien<br> - Allgemeine Richtlinien
[Richtlinien für Sprachanrufe und Anrufe](voice-and-calling-policies.md)| Richtlinien für Sprach- und Anrufanrufe verwalten diese Einstellungen über Teams wie Notrufe, Anrufrouting und Anrufer-ID.
[App-Richtlinien](app-policies.md)| App-Richtlinien werden zum Steuern von Anwendungen in Microsoft Teams. Administratoren können zulassen oder blockieren, welche Apps Benutzer installieren, Anwendungen an die Teams-App-Leiste eines Benutzers anheften und Anwendung im Auftrag Ihrer Benutzer installieren können.
[Messagingrichtlinien](messaging-policies-in-teams.md)| Messagingrichtlinien steuern die Verfügbarkeit von Chats und Kanalfeatures.

## <a name="related-topics"></a>Verwandte Themen

* [Zuweisen von Richtlinien in Teams – Erste Schritte](policy-assignment-overview.md)
* [Verwalten von Feedbackrichtlinien in Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Verwalten von Teamrichtlinien in Microsoft Teams](teams-policies.md)
* [Einrichten von Live-Ereignissen in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams für Education von Richtlinien und Richtlinienpaketen](policy-packages-edu.md)