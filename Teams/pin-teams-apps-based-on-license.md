---
title: Anpassen von Teams-Apps für Ihre Mitarbeiter in Service und Produktion
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über die maßgeschneiderte App-Erfahrung für Mitarbeiter in Service und Produktion in Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b59753e1ad1e5a0be36ed8a0d924d7fa6d6658a2
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675517"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Anpassen von Teams-Apps für Ihre Mitarbeiter in Service und Produktion

> [!NOTE]
> Dieses Feature wird derzeit eingeführt und ist in Ihrer Organisation möglicherweise noch nicht verfügbar. Weitere Informationen zu bevorstehenden Features von Microsoft Teams finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Übersicht

Teams heftet Apps basierend auf der Lizenz an, um Ihren Mitarbeitern in Service und Produktion eine out-of-the-box-Erfahrung in Teams zu bieten, die auf ihre Anforderungen zugeschnitten ist. 

Dank der maßgeschneiderten App-Erfahrung in Service und Produktion erhalten Ihre Mitarbeiter in Service und Produktion die relevantesten Apps in Teams, ohne dass der Administrator eine Aktion ausführen muss.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VuCH]

## <a name="tailored-frontline-app-experience"></a>Maßgeschneiderte App-Erfahrung in Service und Produktion

Apps werden an die App-Leiste angeheftet. Dies ist die Leiste am unteren Rand der Teams mobilen Clients (iOS und Android) und auf der Seite des Teams Desktopclients. Die folgenden Apps sind für Benutzer angeheftet, die über eine [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) verfügen:

- [Aktivität](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Chat](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Microsoft Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie-Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Aufgaben](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Schichten](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Genehmigungen](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams Mobile**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="Die maßgeschneiderte App-Erfahrung in Service und Produktion auf Teams Mobilgeräten" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams Desktop**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="Die maßgeschneiderte App-Erfahrung in Service und Produktion auf Teams Desktop" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Admin Steuerelemente

> [!NOTE]
> Die Einstellung zum **Anheften von Benutzern** muss in der globalen (organisationsweiten Standard-) [App-Setuprichtlinie](teams-app-setup-policies.md) aktiviert sein, damit dieses Feature wirksam wird.

Die maßgeschneiderte App-Erfahrung in Service und Produktion wird durch die Organisationsweite App-Einstellung "**Maßgeschneiderte Apps anzeigen**" auf der Seite ["Apps verwalten](manage-apps.md#manage-org-wide-app-settings)" im Teams Admin Center gesteuert. Wenn das Feature aktiviert ist, erhalten alle Benutzer in Ihrer Organisation, die über eine F-Lizenz verfügen, die maßgeschneiderte App-Erfahrung.

Beachten Sie, dass alle benutzerdefinierten [App-Setuprichtlinien](teams-app-setup-policies.md) , die Benutzern zugewiesen sind, Vorrang haben. Dies bedeutet: Wenn einem Benutzer bereits eine benutzerdefinierte App-Setuprichtlinie zugewiesen ist, erhält der Benutzer die Konfiguration, die in der benutzerdefinierten App-Setuprichtlinie definiert ist. Weitere Informationen zur Funktionsweise des Features mit Teams App-Richtlinien, einschließlich der globalen App-Setuprichtlinie, finden Sie im Abschnitt ["Szenarien"](#scenarios) weiter unten in diesem Artikel.

Diese Funktion ist standardmäßig aktiviert. Wenn Sie die von Microsoft bereitgestellte maßgeschneiderte Frontline-App-Erfahrung jedoch nicht wünschen, können Sie das Feature deaktivieren. So deaktivieren oder aktivieren Sie das Feature:

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **Teams Apps** > **verwalten**, und wählen Sie dann **organisationsweite App-Einstellungen** aus.
2. Schalten **Sie unter "Maßgeschneiderte Apps**" die Option " **Maßgeschneiderte Apps anzeigen** " auf **"Aus** " oder " **Ein**".

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Screenshot der Einstellung &quot;Maßgeschneiderte Apps anzeigen&quot; auf der Seite &quot;Apps verwalten&quot; im Teams Admin Center" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Szenarien

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>Wie wirkt sich die maßgeschneiderte Frontline-App-Erfahrung auf meine globale App-Setuprichtlinie aus?

Erfahren Sie, wie die maßgeschneiderte Frontline-App-Erfahrung mit der globalen App-Setuprichtlinie zusammenarbeitet. Die Szenarien in dieser Tabelle gelten für Mitarbeiter in Service und Produktion, die über eine F-Lizenz und die globale App-Setuprichtlinie verfügen, wobei die **Benutzer-Pinning** aktiviert ist.

|Wenn... |Dann... |
|---------|---------|
|Ein Mitarbeiter in Service und Produktion verfügt über die globale App-Setuprichtlinie, und das Feature ist deaktiviert. |Der Mitarbeiter in Service und Produktion ruft die In der globalen App-Setuprichtlinie definierten Apps ab.|
|Ein Mitarbeiter in Service und Produktion verfügt über die globale App-Setuprichtlinie, und das Feature ist aktiviert.     | Der Mitarbeiter in Service und Produktion erhält die maßgeschneiderte App-Erfahrung in Service und Produktion. Apps, die in der globalen App-Setuprichtlinie definiert sind, werden unter den maßgeschneiderten Apps angeheftet.      |
|Sie aktualisieren die globale App-Setuprichtlinie, und das Feature ist aktiviert.     |Der Mitarbeiter in Service und Produktion erhält die maßgeschneiderte Frontline-App-Erfahrung, und die in der globalen App-Setuprichtlinie definierten Apps werden unter den maßgeschneiderten Apps angeheftet.         |
|Ein Mitarbeiter in Service und Produktion verfügt über die globale App-Setuprichtlinie, und **die Benutzerpinnung** ist deaktiviert. |Der Mitarbeiter in Service und Produktion ruft die In der globalen App-Setuprichtlinie definierten Apps ab.|
|Ein Mitarbeiter in Service und Produktion verfügt über die globale App-Setuprichtlinie, und die globale App-Setuprichtlinie wird geändert, um eine Branchen-App an der zweiten Position in der App-Liste einzuschließen. |Die Branchen-App ist unter den maßgeschneiderten Apps angeheftet. Der Mitarbeiter in Service und Produktion kann die App-Reihenfolge ändern, wenn die **Benutzer-Pinning** aktiviert ist.         |
|Ein Mitarbeiter in Service und Produktion verfügt über die globale Einrichtungsrichtlinie, und die globale App-Setuprichtlinie wird geändert, um Schichten an der ersten Position einzuschließen.  |Schichten werden an die sechste Position angeheftet, wie durch die maßgeschneiderte App-Erfahrung in Service und Produktion definiert. Der Mitarbeiter in Service und Produktion kann die App-Reihenfolge ändern, wenn die **Benutzer-Pinning** aktiviert ist.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>Wie funktioniert die maßgeschneiderte Frontline-App-Erfahrung mit anderen Teams App-Richtlinien?

Erfahren Sie, wie die maßgeschneiderte Frontline-App-Erfahrung mit anderen Teams App-Richtlinien funktioniert.

|Wenn...  |Dann... |
|---------|---------|
Das Feature ist deaktiviert.   | Der Mitarbeiter in Service und Produktion ruft die Apps ab, die in der globalen App-Setuprichtlinie oder der benutzerdefinierten App-Setuprichtlinie definiert sind.          |
|Ein Mitarbeiter in Service und Produktion verfügt über eine benutzerdefinierte App-Setuprichtlinie, und das Feature ist aktiviert.    |Der Mitarbeiter in Service und Produktion ruft die In der benutzerdefinierten App-Setuprichtlinie definierten Apps ab.          |
|Eine App in der maßgeschneiderten Frontline-App-Benutzeroberfläche wird für einen Benutzer oder für Ihre Organisation blockiert.      |Die maßgeschneiderte App-Erfahrung in Service und Produktion berücksichtigt die [App-Berechtigungsrichtlinie](teams-app-permission-policies.md). Wenn eine App blockiert ist, wird dem Mitarbeiter in Service und Produktion die blockierte App nicht angezeigt.           |
|Eine App in der maßgeschneiderten Frontline-App-Umgebung ist bereits in einer App-Setuprichtlinie definiert, und das Feature ist aktiviert. |Die App wird basierend auf der Reihenfolge angeheftet, die in der Liste der maßgeschneiderten Apps definiert ist.        |
|Ein Benutzer verfügt über eine E-, A- oder G-Lizenz, und das Feature ist aktiviert.   | Der Benutzer erhält nicht die maßgeschneiderte App-Erfahrung in Service und Produktion. Derzeit gilt die Erfahrung nur für Benutzer, die über eine F-Lizenz verfügen.        |

> [!NOTE]
> Sie können die Apps oder die Reihenfolge der Apps in der maßgeschneiderten App-Umgebung in Service und Produktion nicht ändern. Wenn Sie vorerst Änderungen vornehmen möchten, können Sie Ihre eigene benutzerdefinierte Benutzeroberfläche einrichten. Deaktivieren Sie dazu zuerst das Feature. [Erstellen Sie dann eine benutzerdefinierte App-Setuprichtlinie](teams-app-setup-policies.md), und [weisen Sie sie Benutzern oder Gruppen zu](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten der Walkie Talkie-App in Teams](walkie-talkie.md)
- [Verwalten der Aufgaben-App in Teams](manage-tasks-app.md)
- [Verwalten der Schichten-App in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Verwalten der Genehmigungen-App in Teams](approval-admin.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
