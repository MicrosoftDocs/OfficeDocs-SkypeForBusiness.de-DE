---
title: Verwalten von Microsoft Teams mit Richtlinien
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
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: acaa1280e00ad2e86a49c2bbd8e7f4464bd0c0e7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268760"
---
# <a name="manage-teams-with-policies"></a>Verwalten von Microsoft Teams mit Richtlinien

Richtlinien sind ein wichtiger Bestandteil der Verwaltung von Teams. Verwenden Sie diesen Artikel, um zu navigieren, wie Sie Richtlinien zum Nutzen Ihrer Organisation verwenden.

## <a name="what-you-use-policies-for"></a>Wofür Sie Richtlinien verwenden

Richtlinien werden verwendet, um viele Aufgaben in Ihrer Organisation in verschiedenen Bereichen wie Messaging, Besprechungen und Anwendungen auszuführen. Sie können beispielsweise zulassen, dass Benutzer Besprechungen in einem Teams-Kanal planen, benutzern das Bearbeiten gesendeter Nachrichten ermöglichen und steuern, ob Benutzer Apps an die Teams-App-Leiste anheften können.

## <a name="how-to-assign-policies"></a>Zuweisen von Richtlinien

Richtlinien können auf verschiedene Arten zugewiesen werden, je nachdem, was Ihre Organisation zu erreichen versucht. Sie können Aufgaben im Teams Admin Center erstellen und anzeigen.

:::image type="content" source="media/group-policy-assignment.png" alt-text="Screenshot der Gruppenrichtlinienzuweisung für Teams." lightbox="media/group-policy-assignment.png":::

Weitere Informationen zum Zuweisen von Richtlinien [finden Sie hier](policy-assignment-overview.md).

> [!NOTE]
> Um die Zuweisung von Richtlinien aufzuheben, können Sie Zuweisungen für alle Benutzer, die einer Richtlinie direkt zugewiesen sind, massenhaft entfernen. Weitere Informationen finden Sie [unter "Aufheben der Zuweisung von Richtlinien in Massen](assign-policies-users-and-groups.md#unassign-policies-in-bulk)".

## <a name="how-to-manage-policies"></a>Verwalten von Richtlinien

Richtlinien werden mit dem Microsoft Teams Admin Center oder [mithilfe von PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell) verwaltet.

Beispielsweise können Sie mit einer App-Setuprichtlinie Benutzern das Hochladen benutzerdefinierter Apps, das Installieren von Apps im Auftrag Ihrer Benutzer und das Anheften von Apps an die Teams-App-Leiste ermöglichen. Diese Richtlinien sind im Teams Admin Center konfiguriert.

:::image type="content" source="media/app-setup-policy.png" alt-text="Screenshot der App-Setuprichtlinie." lightbox="media/app-setup-policy.png":::

Darüber hinaus kann eine Besprechungsrichtlinie verwendet werden, um Audio- und Videoeinstellungen in Teams-Besprechungen wie Transkriptionen, Cloudaufzeichnungen und IP-Audio/Video zu steuern.

:::image type="content" source="media/engineering-meeting-policy.png" alt-text="Screenshot der Besprechungsrichtlinie." lightbox="media/engineering-meeting-policy.png":::

### <a name="teams-for-education"></a>Microsoft Teams für Bildungseinrichtungen

Sie können auch den [Teams für Education Richtlinien-Assistenten](easy-policy-setup-edu.md) verwenden, um Richtlinien für Ihre Lernumgebung einfach einzurichten und zu verwalten.

:::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot des Richtlinien-Assistenten Teams für Education." lightbox="media/easy-policy-setup-quick-setup.png":::

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