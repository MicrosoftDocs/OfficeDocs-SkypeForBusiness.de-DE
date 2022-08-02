---
title: Verwalten von Teams mit Richtlinien
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informieren Sie sich über Teams-Richtlinien.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b56e617321cea25fe677b7d9a7a00afba0940b07
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156533"
---
# <a name="manage-teams-with-policies"></a>Verwalten von Teams mit Richtlinien

Richtlinien sind ein wichtiger Bestandteil der Verwaltung von Teams. Verwenden Sie diesen Artikel, um zu navigieren, wie Sie Richtlinien zum Nutzen Ihrer Organisation verwenden.

## <a name="what-you-use-policies-for"></a>Wofür Sie Richtlinien verwenden

Richtlinien werden verwendet, um viele Aufgaben in Ihrer Organisation in verschiedenen Bereichen wie Messaging, Besprechungen und Anwendungen auszuführen. Sie können beispielsweise zulassen, dass Benutzer Besprechungen in einem Teams-Kanal planen, benutzern das Bearbeiten gesendeter Nachrichten ermöglichen und steuern, ob Benutzer Apps an die Teams-App-Leiste anheften können.

## <a name="how-to-assign-policies"></a>Zuweisen von Richtlinien

Richtlinien können auf verschiedene Arten zugewiesen werden, je nachdem, was Ihre Organisation zu erreichen versucht. Sie können Aufgaben im Teams Admin Center erstellen und anzeigen.

![Screenshot der Gruppenrichtlinienzuweisung.](media/group-policy-assignment.png)

Weitere Informationen zum Zuweisen von Richtlinien [finden Sie hier](policy-assignment-overview.md).

> [!NOTE]
> Um die Zuweisung von Richtlinien aufzuheben, können Sie Zuweisungen für alle Benutzer, die einer Richtlinie direkt zugewiesen sind, massenhaft entfernen. Weitere Informationen finden Sie [unter "Aufheben der Zuweisung von Richtlinien in Massen](assign-policies-users-and-groups.md#unassign-policies-in-bulk)".

## <a name="how-to-manage-policies"></a>Verwalten von Richtlinien

Richtlinien werden mit dem Microsoft Teams Admin Center oder [mithilfe von PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell) verwaltet.

Beispielsweise können Sie mit einer App-Setuprichtlinie Benutzern das Hochladen benutzerdefinierter Apps, das Installieren von Apps im Auftrag Ihrer Benutzer und das Anheften von Apps an die Teams-App-Leiste ermöglichen. Diese Richtlinien sind im Teams Admin Center konfiguriert.

![Screenshot der App-Setuprichtlinie.](media/app-setup-policy.png)

Darüber hinaus kann eine Besprechungsrichtlinie verwendet werden, um Audio- und Videoeinstellungen in Teams-Besprechungen wie Transkriptionen, Cloudaufzeichnungen und IP-Audio/Video zu steuern.

![Screenshot der Besprechungsrichtlinie.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Microsoft Teams für Bildungseinrichtungen

Sie können auch den [Teams für Education Richtlinien-Assistenten](easy-policy-setup-edu.md) verwenden, um Richtlinien für Ihre Lernumgebung einfach einzurichten und zu verwalten.

![Screenshot des Richtlinien-Assistenten Teams für Education.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Richtlinientypen

Die folgenden Richtlinien können mit Microsoft Teams verwaltet werden.

Richtlinientyp | Beschreibung
------------|------------
[Richtlinienpakete](manage-policy-packages.md) | Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Einstellungen, die Sie Benutzern mit ähnlichen Rollen in Ihrer Organisation zuweisen können.
[Besprechungsrichtlinien](meeting-policies-overview.md) | Eine Besprechungsrichtlinie wird verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern in Ihrer Organisation geplant wurden. Besprechungsrichtlinien umfassen die folgenden Themen.<br> – Audio- und Videorichtlinien<br> – Inhalts- und Bildschirmfreigaberichtlinien<br> – Teilnehmer-, Gäste- und Zugriffsrichtlinien<br> - Allgemeine Richtlinien
[VoIP- und Anrufrichtlinien](voice-and-calling-policies.md)| Sprach- und Anrufrichtlinien verwalten diese Einstellungen über Teams wie Notrufe, Anrufweiterleitung und Anrufer-ID.
[App-Richtlinien](app-policies.md)| App-Richtlinien werden verwendet, um Anwendungen in Microsoft Teams zu steuern. Administratoren können zulassen oder blockieren, welche Apps Benutzer installieren können, Anwendungen an die Teams-App-Leiste eines Benutzers anheften und die Anwendung im Namen Ihrer Benutzer installieren.
[Messagingrichtlinien](messaging-policies-in-teams.md)| Messagingrichtlinien steuern die Verfügbarkeit von Chat- und Kanalfeatures.

## <a name="related-topics"></a>Verwandte Themen

* [Zuweisen von Richtlinien in Teams – erste Schritte](policy-assignment-overview.md)
* [Verwalten von Feedbackrichtlinien in Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Verwalten von Teamrichtlinien in Microsoft Teams](teams-policies.md)
* [Einrichten von Live-Ereignissen in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams für Education Richtlinien und Richtlinienpakete](policy-packages-edu.md)