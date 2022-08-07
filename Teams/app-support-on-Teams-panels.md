---
title: Unterstützung von Microsoft Teams-Apps/Branchen-Apps in Teams-Bereichen
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Beschreibt die Unterstützung für Teams-Apps/BRANCHEN-Apps.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75548acc44d1f360e13dd5946e6e39726c744bb6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270680"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Unterstützung von Microsoft Teams-Apps/Branchen-Apps in Teams-Bereichen

Teams-Bereiche fügen Unterstützung für [Teams-Apps/Branchen-Apps hinzu](/microsoftteams/platform/overview). Auf diese Weise können Unternehmen zusätzliche Erfahrungen in den Panels hinzufügen, um die Anforderungen Ihrer Organisation zu erfüllen. Diese Version unterstützt statische Webinhalte.

> [!IMPORTANT]
> Dieses Feature ist nur verfügbar, nachdem Sie Ihre Teams-Panels-Geräte aktualisiert haben. Sie benötigen die Version 1449/1.0.97.2021070601 der Teams-App oder höher, um App-Unterstützung in Teams-Bereichen zu erhalten.

## <a name="teams-app-experience-on-teams-panels"></a>Teams-App-Erfahrung in Teams-Bereichen

![Screenshot des Teams Admin Centers mit dem Abschnitt, in dem Benutzer zu Apps navigieren können.](media/tac1update.png)

*Der Startbildschirm der Teams-Bereiche enthält App-Navigationsoptionen, die im Screenshot rot dargestellt sind. Beachten Sie, dass dies Beispielsymbole sind und möglicherweise nicht zur Verwendung verfügbar sind.*

![Screenshot der App-Canvas, in der Apps hinzugefügt werden können.](media/appscreen.png)

*Wenn ein Endbenutzer auf eines der App-Symbole tippt, wird der Teams-App-Bildschirm im vorherigen Screenshot angezeigt. Das graue Rechteck im Screenshot ist der Ort, an dem Apps auf der Teams-Türschild angezeigt werden. Die App-Leiste ist fest und Teil der Teams-Panels-App.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Einrichten und Verwalten von Teams-Panels-Apps im Teams Admin Center

Microsoft Teams-Apps bringen wichtige Informationen, gängige Tools und vertrauenswürdige Prozesse an die Stelle, an der sich Die Benutzer sammeln, lernen und arbeiten. Teams-Apps arbeiten [mit integrierten Funktionen](/microsoftteams/platform/concepts/capabilities-overview). Als IT-Administrator haben Sie nun die Wahl, welche Apps in das Gerät für Teams-Bereiche Ihrer Organisation aufgenommen werden sollen, und Berechtigungen über das [Teams Admin Center](https://admin.teams.microsoft.com/) anzupassen.

Sie können jetzt die Teams-Apps in Teams-Bereichen verwenden und die Benutzeroberfläche basierend auf den Anforderungen Ihrer Organisation anpassen. Sie können entscheiden, auf welche Web-App Ihre Benutzer zugreifen und die App-Ansichten verwenden und priorisieren können. Einige Optionen, z. B. die Bot- und Messaging-Funktionen, werden derzeit nicht unterstützt. Erfahren Sie mehr über [die Teams-Apps](/microsoftteams/platform/overview) und [wie Sie Ihre Geräte in Microsoft Teams verwalten](/microsoftteams/devices/device-management).

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Verwalten von Apps in Teams-Bereichen im Teams Admin Center

**Hinweis**: Sie müssen ein globaler Administrator oder ein Teams-Dienstadministrator sein, um auf das [Teams Admin Center](https://admin.teams.microsoft.com/) zugreifen zu können.

Endbenutzer können Apps in Teams-Bereichen anzeigen, aber nicht installieren. Als Administrator können Sie alle Teams-Apps für Ihre Organisation über das Teams Admin Center anzeigen und verwalten. Erfahren Sie mehr darüber, wie Sie [Ihre Apps im Microsoft Teams Admin Center](/microsoftteams/manage-apps) über die Seite **"Apps verwalten"** verwalten können. Auf der Seite **"Apps verwalten** " im Teams Admin Center können Sie auch [benutzerdefinierte Apps](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store) hochladen.

Nach dem Einrichten von Apps können Sie [App-Berechtigungsrichtlinien](/microsoftteams/teams-app-permission-policies) und [App-Setuprichtlinien](/microsoftteams/teams-app-setup-policies) verwenden, um die App-Erfahrung für bestimmte Raumkonten in Ihrer Organisation zu konfigurieren.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Anheften von Apps in Teams-Bereichen mit App-Setuprichtlinien

Da Teams die Möglichkeit bietet, eine breite Palette von Apps anzuzeigen, können Administratoren entscheiden, welche Apps für die Organisation am wichtigsten sind, und nur diese für den **Startbildschirm** der Teams-Bereiche anheften, um schnell darauf zugreifen zu können. Wenn mehr als fünf angeheftete Apps oder nicht angeheftete Apps vorhanden sind, werden sie unter dem Bildschirm " **Mehr** " angezeigt. Microsoft empfiehlt das Erstellen einer benutzerdefinierten App-Setuprichtlinie speziell für Teams-Bereiche.

![Screenshot der Benutzeroberfläche der Seite "App-Setuprichtlinien".](media/appsetup1.png)

Um angeheftete Apps zu verwalten, die in den Teams-Bereichen angezeigt werden, melden Sie sich beim Teams Admin Center für Ihre Organisation an, und navigieren Sie zu **Setuprichtlinien** \> für **Teams-Apps** \> **: Auswählen oder Erstellen einer neuen Richtlinie** \> **angeheftete Apps**.

![Screenshot des Abschnitts "Angeheftete Apps" auf der Benutzeroberfläche.](media/appsetup2.png)

*In diesem Bild enthaltene Apps sind nur Beispiele und stehen möglicherweise nicht zur Verwendung zur Verfügung.*

Microsoft empfiehlt, **dass Sie "Benutzerdefinierte Apps hochladen** " und " **Benutzeranheftung** " deaktivieren, um die beste Teams-App-Erfahrung in Teams-Bereichen zu erzielen.

Weitere Informationen zum Anheften von Apps finden [Sie unter Verwalten von App-Setuprichtlinien](/microsoftteams/teams-app-setup-policies).

## <a name="manage-apps-display-order-in-teams-panels"></a>Verwalten der Anzeigereihenfolge von Apps in Teams-Bereichen

![Screenshot des Abschnitts "Apps" auf der Benutzeroberfläche.](media/appsetup3.png)

*In diesem Bild enthaltene Apps sind nur Beispiele und stehen möglicherweise nicht zur Verwendung zur Verfügung.*

Um die Reihenfolge zu verwalten, in der Apps in den Teams-Bereichen angezeigt werden, melden Sie sich beim Teams Admin Center für Ihre Organisation an, und navigieren Sie zu Den Richtlinien für das **Einrichten** \> von **Teams-Apps** \> **wählen Sie die angehefteten Richtlinien-Apps** \> **aus:** **Nach oben/unten verschieben**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Zuweisen von Setuprichtlinien zu einem Raumressourcenkonto

Nach dem Erstellen der Setuprichtlinie muss der Administrator diese Richtlinie dem Raumressourcenkonto zuweisen, das bei den Teams-Bereichen angemeldet wird. Weitere Informationen finden [Sie unter Zuweisen von Richtlinien zu Benutzern und Gruppen](/microsoftteams/assign-policies-users-and-groups).

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Wie lange dauert es, bis Teams-Panels die neuen oder aktualisierten App-Setuprichtlinien erhalten?

Nach dem Bearbeiten oder Zuweisen neuer Richtlinien im Teams Admin Center kann es bis zu 24 Stunden dauern, bis Änderungen wirksam werden. Administratoren können versuchen, sich über den Bereich abzumelden/sich anzumelden, auf das Symbol **"Einstellungen"** zu tippen und zurück zum **Startbildschirm** zu wechseln, um zu versuchen, die Richtlinien zu aktualisieren.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Was ist die Reihenfolge der Apps auf dem Bildschirm "Mehr"?

Auf der Seite **"Weitere** Apps" werden die angehefteten Apps zuerst angezeigt. Anschließend werden alle anderen installierten Apps in alphabetischer Reihenfolge angezeigt.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Warum werden Bot-Apps nicht in Teams-Bereichen angezeigt?

Derzeit werden nur statische Registerkarten-Webinhalte unterstützt.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Warum werden native Teams-Apps wie Kalender und Aufgaben nicht in Teams-Bereichen angezeigt?

Native Teams-Apps wie Kalender und Aufgaben werden in Teams-Bereichen nicht angezeigt.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Was ist im Teams Admin Center unter dem Abschnitt "Setuprichtlinien" der Unterschied zwischen installierten Apps und angehefteten Apps?

Für Teams-Bereiche empfiehlt Microsoft die Verwendung angeheftete Apps, damit der Administrator die gewünschte App auswählen und seine Reihenfolge neu anordnen kann.

**Hinweis:** Einige Apps unterstützen das Anheften von Apps nicht. Wenden Sie sich an den App-Entwickler, um die App-Anheftfunktion zu aktivieren.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Warum werden andere Apps auf dem Bildschirm "Mehr" angezeigt, obwohl sie nicht Teil der installierten oder angehefteten Apps im Richtlinienabschnitt zum Einrichten von Teams-Apps sind?

Wenn Apps zuvor über andere App-Richtlinien oder manuell in den Teams-Desktop-/Webclients für das in Teams-Bereichen verwendete Raumressourcenkonto installiert wurden, muss sich der Administrator möglicherweise beim Raumressourcenkonto in Teams anmelden und die Apps manuell deinstallieren, indem er mit der rechten Maustaste auf die App klickt und dann **"Deinstallieren**" auswählt.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich im Bereich "Angeheftete Apps hinzufügen" keine App finden?

Nicht alle Apps können über eine App-Setuprichtlinie an Teams angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um Apps zu finden, die angeheftet werden können, suchen Sie im Bereich " **Angeheftete Apps hinzufügen** " nach der App. Weitere Informationen finden Sie [in den häufig gestellten Fragen unter "Arbeiten mit App-Setuprichtlinien](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)".

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>Warum wird im Bereich "Setuprichtlinien" ein Popup "Benutzer anheften" angezeigt, nachdem ich "Benutzerpinning" deaktiviert habe?

![Screenshot des Abschnitts "Setuprichtlinie" auf der Benutzeroberfläche mit einem Popup, das bestätigt, dass die Benutzer-Anheftung aktiv ist.](media/appsetup4.png)

*In diesem Bild enthaltene Apps sind nur Beispiele und stehen möglicherweise nicht zur Verwendung zur Verfügung.*

Dieses Verhalten wird für ein Gerät in einem freigegebenen Bereich erwartet und verhindert unbeabsichtigtes Anheften von Apps.
