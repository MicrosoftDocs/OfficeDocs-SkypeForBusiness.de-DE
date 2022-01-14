---
title: Anpassen Ihrer Teams basierend auf einer Lizenz
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Teams-Apps für Benutzer in Ihrer Organisation basierend auf einer Lizenz anheften.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c94a84d7d331122145ebec1324ec5a88eabbca82
ms.sourcegitcommit: c7904086e6956ad8d0e5544530bcc90d608b6e6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2022
ms.locfileid: "62040002"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>Anpassen Ihrer Teams basierend auf einer Lizenz

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> Dieses Feature gilt derzeit für F-Lizenzen. Der Schwerpunkt dieses Artikels liegt daher auf der Erfahrung von Frontline-Workern. Andere Lizenztypen werden in Zukunft unterstützt.

## <a name="overview"></a>Übersicht

Teams bietet eine Möglichkeit zum Anheften von Apps basierend auf einer Lizenz. Wenn sich ein Benutzer bei einem Teams aktivierten maßgeschneiderte App-Erfahrung meldet, erhält der Benutzer eine App-Erfahrung, die auf seine Lizenz zugeschnitten ist.

Mit diesem Feature erhalten Benutzer die relevantesten Apps in Teams ohne eine vom Administrator benötigte Aktion.

## <a name="tailored-app-experience"></a>Maßgeschneiderte App-Erfahrung

Apps werden an die App-Leiste angeheftet, bei der es sich um die Leiste an der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients (iOS und Android) handelt.

Angeheftete Apps für Benutzer mit einer F-Lizenz:

- Aktivität
- Chat
- Teams
- Schichten
- Aufgaben
- Walkie-Talkie

## <a name="admin-controls"></a>Administratorsteuerelemente

> [!NOTE]
> Das Anheften von Benutzern muss in der globalen (organisationsweiten Standard-)App-Setuprichtlinie aktiviert sein, damit dieses Feature wirksam wird. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

Das Feature "Maßgeschneiderte App-Erfahrung" wird durch die Einstellung Maßgeschneiderte Apps basierend auf Lizenzen organisationsweit anzeigen auf der Seite Apps verwalten im Teams Admin Center gesteuert.  [](manage-apps.md#manage-org-wide-app-settings) Wenn das Feature aktivieren, erhalten alle Benutzer in Ihrer Organisation, die über eine F-Lizenz verfügen, die maßgeschneiderte App-Erfahrung.

Beachten Sie, dass alle Benutzerdefinierten Richtlinien für die App-Einrichtung, die Benutzern zugewiesen sind, Vorrang haben. Wenn einem Benutzer also bereits eine benutzerdefinierte App-Setuprichtlinie zugewiesen ist, erhält der Benutzer die Konfiguration, die in der Benutzerdefinierten App-Setuprichtlinie definiert ist. Weitere Informationen zur Funktionsweise des Features mit vorhandenen App-Setuprichtlinien, die [](#scenarios) Sie in Ihrer Organisation angewendet haben, finden Sie im Abschnitt Szenarien in diesem Artikel.

Diese Funktion ist standardmäßig aktiviert. Wenn Sie jedoch nicht möchten, dass die maßgeschneiderte App-Erfahrung von Microsoft bereitgestellt wird, können Sie die Einstellung deaktivieren. So aktivieren oder deaktivieren Sie das Feature:

1. Wechseln Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Teams Apps** Apps verwalten , und wählen Sie dann  >   **Organisationsweite App-Einstellungen aus.**
2. Schalten Sie **maßgeschneiderte Apps basierend auf Lizenzen anzeigen** auf **Aus** oder **Ein.** 

    :::image type="content" source="media/pin-teams-apps-based-on-license.png" alt-text="Screenshot der Seite "Apps verwalten" mit der Einstellung "Maßgeschneiderte Apps basierend auf einer organisationsweiten Lizenz anzeigen"" lightbox="media/pin-teams-apps-based-on-license.png":::

## <a name="scenarios"></a>Szenarien

Verwenden Sie die Informationen in dieser Tabelle, um zu erfahren, wie das Feature "maßgeschneiderte App-Erfahrung" in verschiedenen Szenarien funktioniert, z. B. wenn Sie vorhandene App-Setuprichtlinien angewendet haben.

|Wenn...  |Dann... |
|---------|---------|
|Ein Benutzer verfügt über die globale App-Setuprichtlinie, und das Feature ist ein.     | Der Benutzer erhält die angepasste App-Erfahrung.        |
|Ein Benutzer verfügt über eine benutzerdefinierte App-Setuprichtlinie, und das Feature ist ein.    |Der Benutzer erhält die Konfiguration, die in der Benutzerdefinierten App-Setuprichtlinie definiert ist.          |
|Das Feature ist verfügbar, und Sie aktualisieren die Globale App-Setuprichtlinie.     |Der Benutzer erhält die angepasste App-Erfahrung basierend auf seiner Lizenz. Die in der globalen App-Setuprichtlinie definierten Apps sind weiterhin angeheftet und werden weiter unten in der Liste der angeheftet Apps angezeigt.          |
|Das Feature ist deaktiviert.   | Der Benutzer erhält die Erfahrung, die in der globalen App-Setuprichtlinie oder der benutzerdefinierten App-Setuprichtlinie definiert ist, die ihm zugewiesen ist.          |
|Ein Benutzer verfügt über eine E-, A- oder G-Lizenz, und das Feature ist ein.   | Der Benutzer hat keine angepasste App-Erfahrung. Derzeit gilt die angepasste App-Erfahrung nur für Benutzer, die über eine F-Lizenz verfügen.        |
|Eine App für die angepasste App-Erfahrung wird für einen Benutzer oder für Ihre Organisation blockiert.      |Die maßgeschneiderte App-Erfahrung berücksichtigt die App-Berechtigungsrichtlinie. Wenn eine App blockiert ist, wird die blockierte App für Benutzer nicht angezeigt.           |
|Eine App für die angepasste App-Erfahrung ist bereits in einer App-Setuprichtlinie definiert, und das Feature ist ein. |Die App wird basierend auf der durch die angepasste App-Erfahrung definierten Reihenfolge angeheftet.        |

> [!NOTE]
> Sie können die Apps oder die Reihenfolge von Apps nicht in der angepassten App-Erfahrung ändern. Wenn Sie Änderungen vornehmen möchten, können Sie vorerst eine eigene benutzerdefinierte Benutzerdefinierte Einrichten. Deaktivieren Sie dazu zuerst das Feature. Erstellen Sie dann [eine benutzerdefinierte App-Setuprichtlinie](teams-app-setup-policies.md), und weisen [Sie sie Benutzern oder Gruppen zu.](assign-policies-users-and-groups.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
