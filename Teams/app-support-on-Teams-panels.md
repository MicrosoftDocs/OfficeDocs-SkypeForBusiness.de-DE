---
title: Microsoft Teams apps/Line of Business (LOB) app support on Teams panels
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Beschreibt die Unterstützung Teams Apps/Branchen-Apps.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8852ef3d212d2a284f4af72662c771d4c13b13af
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205635"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams apps/Line of Business (LOB) app support on Teams panels

Teams -Panels wird Unterstützung für [Teams-Apps/Branchen-Apps hinzugefügt.](/microsoftteams/platform/overview) Auf diese Weise können Unternehmen zusätzliche Erfahrungen mit den Panels hinzufügen, die den Anforderungen Ihrer Organisation entsprechen. Diese Version unterstützt statische Webinhalte.

> [!IMPORTANT]
> Dieses Feature ist nur nach dem Update Ihrer Teams-Panels verfügbar. Sie benötigen die Teams-App, Version 1449/1.0.97.2021070601 oder neuer, um App-Unterstützung innerhalb Teams zu haben.

## <a name="teams-app-experience-on-teams-panels"></a>Teams der App auf Teams-Panels

![Screenshot des Teams Admin Centers, der zeigt, in welchem Abschnitt Benutzer zu Apps navigieren können.](media/tac1update.png) 

*Die Teams-Panels enthält App-Navigationsoptionen, die im Screenshot rot umrissen sind. Beachten Sie, dass es sich hier um Beispielsymbole handelt, die möglicherweise nicht verwendet werden können.*

![Screenshot der App-Canvas, auf der Apps hinzugefügt werden können.](media/appscreen.png)

*Wenn ein Endbenutzer auf eines der App-Symbole tippt, wird der im vorherigen Screenshot Teams Bildschirm der App angezeigt. Das graue Rechteck im Screenshot ist der Bereich, an dem Apps im Teams werden. Die App-Leiste ist fest und Teil der App Teams Panels.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Einrichten und Verwalten von Teams-Panels im Teams Admin Center 

Microsoft Teams-Apps bringen wichtige Informationen, allgemeine Tools und vertrauenswürdige Prozesse an die Stelle, an der personen sammeln, lernen und arbeiten. Teams-Apps können [integrierte Funktionen nutzen.](/microsoftteams/platform/concepts/capabilities-overview) Als IT-Administrator haben Sie jetzt die Wahl, welche Apps sie in das Teams-Panels-Gerät Ihrer Organisation einblenden und Berechtigungen über das Teams [Admin Center anpassen.](https://admin.teams.microsoft.com/)

Sie können jetzt die Teams-Apps in Teams-Panels verwenden und die Benutzeroberfläche an die Anforderungen Ihrer Organisation anpassen. Sie können entscheiden, auf welche Web-App Ihre Benutzer zugreifen und die App-Ansichten verwenden und priorisieren können. Einige Optionen, z. B. bot- und messaging-Funktionen, werden derzeit nicht unterstützt. Weitere Informationen zu [den Teams-Apps](/microsoftteams/platform/overview) und zum [Verwalten Ihrer Geräte in Microsoft Teams.](/microsoftteams/devices/device-management)

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Verwalten von Apps in Teams-Panels im Teams Admin Center

**Hinweis:** Sie müssen ein globaler Administrator oder ein Teams-Dienstadministrator sein, um auf das Teams [Admin Center zugreifen zu können.](https://admin.teams.microsoft.com/)

Endbenutzer können Apps auf einem Teams anzeigen, Teams installieren. Als Administrator können Sie alle Ihre Teams über das Teams Admin Center anzeigen und verwalten. Weitere Informationen dazu, wie Sie Ihre Apps verwalten können, finden Sie [im Microsoft Teams Admin Center](/microsoftteams/manage-apps) über die Seite **"Apps verwalten".** Auf **der Seite Apps** verwalten im Teams Admin Center können Sie auch benutzerdefinierte Apps [hochladen.](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

Nach dem Einrichten von Apps können [](/microsoftteams/teams-app-setup-policies) Sie [App-Berechtigungsrichtlinien](/microsoftteams/teams-app-permission-policies) und Richtlinien für die App-Einrichtung verwenden, um die App-Benutzererfahrung für bestimmte Raumkonten in Ihrer Organisation zu konfigurieren.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Anheften von Apps an Teams Panels mit Richtlinien für die App-Einrichtung

Da Teams die Möglichkeit bietet, eine Vielzahl von Apps anzuzeigen, können Administratoren entscheiden, welche Apps für die Organisation am  wichtigsten sind, und nur diese für den Startbildschirm der Teams-Panels anheften, um schnell darauf zugreifen zu können. Wenn mehr als fünf angeheftet Apps oder nicht angeheftet Apps verfügbar sind, werden sie unter dem Bildschirm **Mehr** angezeigt. Microsoft empfiehlt das Erstellen einer benutzerdefinierten App-Setuprichtlinie speziell für Teams Panels.

![Screenshot der Benutzeroberfläche der Seite mit den Richtlinien für die App-Einrichtung](media/appsetup1.png) 

Zum Verwalten von angeheftet Apps, die in den Teams-Panels angezeigt werden, melden Sie sich beim Teams Admin Center für Ihre Organisation an, und navigieren Sie zu Den Setuprichtlinien für **Teams-Apps** Auswählen oder Erstellen einer neuen Richtlinie Angeheftet \>  \>  \> Apps.

![Screenshot des Abschnitts "Angeheftet Apps" auf der Benutzeroberfläche](media/appsetup2.png) 

*Die in diesem Bild enthaltenen Apps sind nur Beispiele und können möglicherweise nicht verwendet werden.*

Microsoft empfiehlt, dass Sie **Hochladen** Apps  und Benutzeranheftungen deaktivieren, um die bestmögliche Benutzererfahrung Teams App auf Teams zu erhalten.

Weitere Informationen zum Anheften von Apps finden Sie unter [Verwalten von Richtlinien für die App-Einrichtung.](/microsoftteams/teams-app-setup-policies)

## <a name="manage-apps-display-order-in-teams-panels"></a>Verwalten der Anzeigereihenfolge von Apps in Teams Panels 

![Screenshot des Abschnitts "Apps" auf der Benutzeroberfläche](media/appsetup3.png)

*Die in diesem Bild enthaltenen Apps sind nur Beispiele und können möglicherweise nicht verwendet werden.*

Um die Reihenfolge zu verwalten, in der Apps in den Teams-Panels angezeigt werden, melden Sie sich beim Teams Admin Center für Ihre Organisation an, und navigieren Sie zu Richtlinien für die Einrichtung von **Teams-Apps** Wählen Sie die Richtlinie Angeheftet \>  \>  \> **Apps:** **Nach oben/unten** aus.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Zuweisen von Setuprichtlinien zu einem Raumressourcenkonto

Nach dem Erstellen der Setuprichtlinie muss der Administrator diese Richtlinie dem Konto für Raumressourcen zuweisen, das bei den Teams wird. Weitere Informationen finden Sie unter [Zuweisen von Richtlinien zu Benutzern und Gruppen.](/microsoftteams/assign-policies-users-and-groups)

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Wie lange dauert es, bis Teams neue oder aktualisierte App-Setuprichtlinien erhalten?

Nach dem Bearbeiten oder Zuweisen neuer Richtlinien im Teams Admin Center kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden. Administratoren können versuchen, sich über den Bereich ab- oder abmelden, auf das  **Symbol Einstellungen** tippen und zum Startbildschirm zurück wechseln, um zu versuchen, die Richtlinien zu aktualisieren.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Wie ordnen sich die Apps auf dem Bildschirm "Mehr" an?

Auf der **Seite** Weitere Apps werden die angeheftet Apps zuerst angezeigt. Dann werden alle anderen installierten Apps in alphabetischer Reihenfolge angezeigt.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Warum werden Bot-Apps nicht in Teams angezeigt?

Derzeit werden nur statische Registerkarten-Webinhalte unterstützt.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Warum werden systemeigene Teams, z. B. Kalender und Aufgaben, nicht in Teams angezeigt?

Native Teams-Apps, z. B. Kalender und Aufgaben, werden in den Teams angezeigt.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Was ist im Teams Admin Center im Abschnitt Setuprichtlinien der Unterschied zwischen installierten und angeheftet Apps?

Für Teams-Panels empfiehlt Microsoft die Verwendung angehefteter Apps, damit der Administrator die gewünschte App auswählen und ihre Anordnung ändern kann.

**Hinweis:** Einige Apps unterstützen das Anheften von Apps nicht. Wenden Sie sich an den App-Entwickler, um die Funktion zum Anheften von Apps zu aktivieren.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Warum werden andere Apps im Bildschirm "Mehr" angezeigt, obwohl sie nicht Teil der installierten oder angeheftet Apps im Abschnitt Teams-App-Setuprichtlinie sind?

Wenn Apps zuvor über andere App-Richtlinien oder manuell in den Teams-Desktop-/Webclients für das in Teams-Panels verwendete Raumressourcenkonto installiert wurden, muss sich der Administrator möglicherweise beim Raumressourcenkonto in Teams anmelden und die Apps manuell deinstallieren, indem er mit der rechten Maustaste auf die App klickt und dann Deinstallieren aus **wählt.**

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich im Bereich "Angeheftet Apps hinzufügen" keine App finden?

Nicht alle Apps können über eine App-Teams an die App angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um apps zu finden, die angeheftet werden können, suchen Sie im Bereich **Angeheftet** Apps hinzufügen nach der App. Weitere Informationen finden Sie unter Häufig gestellte Fragen [unter Arbeiten mit Richtlinien für das Einrichten von Apps.](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>Warum wird im Bereich "Setuprichtlinien" ein Popupfenster "Benutzerheftung" angezeigt, nachdem ich "Benutzer anheften?" deaktiviert habe

![Screenshot des Abschnitts "Setuprichtlinie" auf der Benutzeroberfläche mit einem Popupfenster, in dem bestätigt wird, dass das Anheften von Benutzern aktiv ist.](media/appsetup4.png)

*Die in diesem Bild enthaltenen Apps sind nur Beispiele und können möglicherweise nicht verwendet werden.* 

Dieses Verhalten wird für ein Gerät an einem gemeinsam genutzten Bereich erwartet und hilft, unbeabsichtigtes Anheften von Apps zu verhindern.
