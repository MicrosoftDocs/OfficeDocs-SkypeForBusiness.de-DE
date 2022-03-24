---
title: Anpassen Teams Apps für Ihre Mitarbeiter an vorder frontline
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über die angepasste App-Erfahrung für Mitarbeiter in frontline Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774184"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Anpassen Teams Apps für Ihre Mitarbeiter an vorder frontline

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>Übersicht

Teams stellt eine einfache Möglichkeit zum Anheften von Apps für Mitarbeiter in der Frontlinie zur Verfügung. Dieses Feature heftt Apps basierend auf einer Lizenz an, um Ihren Frontline-Mitarbeitern eine individuelle, auf ihre Anforderungen zugeschnittene Teams Einsatzerfahrung zu ermöglichen.

Mit der maßgeschneiderten Frontline-App-Erfahrung erhalten Ihre Mitarbeiter in der Frontline die relevantesten Apps in Teams ohne eine vom Administrator benötigte Aktion.

## <a name="tailored-frontline-app-experience"></a>Maßgeschneiderte Frontline-App-Erfahrung

Apps werden an die App-Leiste angeheftet. Dabei handelt es sich um die Leiste am unteren Rand der mobilen Teams-Clients (iOS und Android) und auf der Seite des Teams-Desktopclients. Die folgenden Apps sind für Benutzer mit einer [F-Lizenz angeheftet](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt):

- [Aktivität](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Chat](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Microsoft Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie-Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Aufgaben](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Schichten](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Genehmigungen](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams Mobile**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="Die maßgeschneiderte Frontline-App-Erfahrung auf Teams Mobile" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams Desktop**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="Die maßgeschneiderte Frontline-App-Erfahrung auf Teams Desktops" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Administratorsteuerelemente

> [!NOTE]
> Die **Einstellung Für das Anheften von** Benutzern muss in der globalen (organisationsweiten Standard [-)](teams-app-setup-policies.md) Setuprichtlinie für Apps aktiviert sein, damit dieses Feature wirksam wird.

Die maßgeschneiderte Frontline-App-Erfahrung wird durch  die Einstellung Für maßgeschneiderte Apps anzeigen auf der Seite Apps [](manage-apps.md#manage-org-wide-app-settings) verwalten im Teams Admin Center gesteuert. Wenn das Feature aktivieren, erhalten alle Benutzer in Ihrer Organisation, die über eine F-Lizenz verfügen, die maßgeschneiderte App-Erfahrung.

Beachten Sie, dass alle Benutzerdefinierten [Richtlinien für die App-Einrichtung,](teams-app-setup-policies.md) die Benutzern zugewiesen sind, Vorrang haben. Wenn einem Benutzer also bereits eine benutzerdefinierte App-Setuprichtlinie zugewiesen ist, erhält der Benutzer die Konfiguration, die in der Benutzerdefinierten App-Setuprichtlinie definiert ist. Weitere Informationen zur Funktionsweise des Features mit Richtlinien für Teams-Apps, einschließlich der globalen Richtlinie für das Einrichten von Apps, finden Sie [](#scenarios) im Abschnitt Szenarien weiter später in diesem Artikel.

Diese Funktion ist standardmäßig aktiviert. Wenn Sie jedoch nicht möchten, dass die maßgeschneiderte Frontline-App-Erfahrung von Microsoft bereitgestellt wird, können Sie das Feature deaktivieren. So aktivieren oder deaktivieren Sie das Feature:

1. Wechseln Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Teams AppsVer** >  dient zum Verwalten von Apps, und wählen Sie **dann Organisationsweite App-Einstellungen aus**.
2. Schalten **Sie unter** Maßgeschneiderte **Apps den Schalter** Maßgeschneiderte Apps anzeigen auf **Aus** oder **Ein**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Screenshot der Einstellung "Maßgeschneiderte Apps anzeigen" auf der Seite "Apps verwalten" im Teams Admin Center" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Szenarien

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>Wie wirkt sich die angepasste Frontline-App-Erfahrung auf meine globale App-Setuprichtlinie aus?

Hier erfahren Sie, wie die maßgeschneiderte Frontline-App-Erfahrung in Zusammenarbeit mit der globalen App-Setuprichtlinie funktioniert. Die Szenarien in dieser Tabelle gelten für Frontline-Workers, die über eine F-Lizenz verfügen, und für die globale App-Setuprichtlinie, bei der **Benutzer-Pinning** aktiviert ist.

|Wenn... |Dann... |
|---------|---------|
|Ein Frontline-Worker verfügt über die globale App-Setuprichtlinie, und das Feature ist deaktiviert. |Der Frontline-Worker ruft die Apps ab, die in der globalen App-Setuprichtlinie definiert sind.|
|Ein Frontline-Worker verfügt über die globale App-Setuprichtlinie, und das Feature ist ein.     | Der Frontline-Worker erhält die maßgeschneiderte Frontline-App-Erfahrung. Apps, die in der globalen App-Setuprichtlinie definiert sind, werden unter den angepassten Apps angeheftet.      |
|Sie aktualisieren die Globale App-Setuprichtlinie, und das Feature ist ein.     |Der Frontline-Worker erhält die angepasste Frontline-App-Erfahrung, und die in der globalen App-Setuprichtlinie definierten Apps sind unter den angepassten Apps angeheftet.         |
|Ein Frontline-Worker verfügt über die globale Richtlinie für die App-Einrichtung, und **das Anheften von** Benutzern ist deaktiviert. |Der Frontline-Worker ruft die Apps ab, die in der globalen App-Setuprichtlinie definiert sind.|
|Ein Frontline-Worker verfügt über die Richtlinie für die globale App-Einrichtung, und die Richtlinie für die globale App-Einrichtung wird geändert, um eine Branchen-App an der zweiten Position in der App-Liste hinzuzufügen. |Die Branchen-App ist unterhalb der angepassten Apps angeheftet. Der Frontline-Worker kann die App-Reihenfolge ändern, wenn **das Anheften durch** den Benutzer ein ist.         |
|Ein Frontline-Worker verfügt über die globale Setuprichtlinie, und die Richtlinie für die globale App-Einrichtung wird so geändert, dass Schichten an der ersten Position enthalten sind.  |Schichten werden an die sechste Position angeheftet, wie durch die angepasste Frontline-App-Erfahrung definiert. Der Frontline-Worker kann die App-Reihenfolge ändern, wenn **das Anheften durch** den Benutzer ein ist.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>Wie funktioniert die maßgeschneiderte Frontline-App-Erfahrung mit anderen Richtlinien Teams App?

Erfahren Sie, wie die maßgeschneiderte Frontline-App-Erfahrung mit anderen Richtlinien Teams App funktioniert.

|Wenn...  |Dann... |
|---------|---------|
Das Feature ist deaktiviert.   | Der Frontline-Worker ruft die Apps ab, die in der globalen App-Setuprichtlinie oder der benutzerdefinierten App-Setuprichtlinie definiert sind.          |
|Ein Frontline-Worker verfügt über eine benutzerdefinierte App-Setuprichtlinie, und das Feature ist ein.    |Der Frontline-Worker ruft die Apps ab, die in der benutzerdefinierten App-Setuprichtlinie definiert sind.          |
|Eine App in der maßgeschneiderten Frontline-App-Benutzeroberfläche wird für einen Benutzer oder für Ihre Organisation blockiert.      |Die maßgeschneiderte Frontline-App-Erfahrung berücksichtigt die [App-Berechtigungsrichtlinie](teams-app-permission-policies.md). Wenn eine App blockiert ist, wird die blockierte App dem Frontline-Worker nicht angezeigt.           |
|Eine App für die maßgeschneiderte Frontline-App-Erfahrung ist bereits in einer App-Setuprichtlinie definiert, und das Feature ist auf ein festgelegt. |Die App wird basierend auf der reihenfolge angeheftet, die in der Liste der angepassten Apps definiert ist.        |
|Ein Benutzer verfügt über eine E-, A- oder G-Lizenz, und das Feature ist ein.   | Der Benutzer sieht die maßgeschneiderte Frontline-App-Erfahrung nicht. Derzeit gilt diese Erfahrung nur für Benutzer, die über eine F-Lizenz verfügen.        |

> [!NOTE]
> Sie können die Apps oder die Reihenfolge von Apps in der maßgeschneiderten Frontline-App-Erfahrung nicht ändern. Wenn Sie Änderungen vornehmen möchten, können Sie vorerst eine eigene benutzerdefinierte Benutzerdefinierte Einrichten. Deaktivieren Sie dazu zuerst das Feature. Erstellen Sie dann [eine benutzerdefinierte App-Setuprichtlinie](teams-app-setup-policies.md), und weisen [Sie sie Benutzern oder Gruppen zu](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten der Walkie-Talkie-App in Teams](walkie-talkie.md)
- [Verwalten der Aufgaben-App in Teams](manage-tasks-app.md)
- [Verwalten der Schichten-App in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Verwalten der Genehmigungen-App in Teams](approval-admin.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
