---
title: Microsoft Teams-Apps/Branchen-App-Unterstützung für Teams Branchen-Apps
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
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb6950bbb78bf04b01194bbab5ec6d9030a53137
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235736"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams-Apps/Branchen-App-Unterstützung für Teams Branchen-Apps

Teams-Panels wird Unterstützung für Teams/Branchen-Apps hinzugefügt. Auf diese Weise können Unternehmen zusätzliche Erfahrungen mit den Panels hinzufügen, die den Anforderungen Ihrer Organisation entsprechen. Diese Version unterstützt statische Webinhalte.

> [!IMPORTANT]
> Dieses Feature ist nur nach dem Update Ihrer Teams-Panels verfügbar. Sie müssen über die Teams-App, Version 1449/1.0.97.2021070601 oder neuer verfügen, damit die App in Teams-Panels unterstützt wird.

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Einrichten und Verwalten Teams Panels im Teams Admin Center 

Microsoft Teams-Apps bringen wichtige Informationen, allgemeine Tools und vertrauenswürdige Prozesse an die Stelle, an der personen sammeln, lernen und arbeiten. Teams-Apps nutzen [integrierte Funktionen .](/platform/concepts/capabilities-overview) Als IT-Administrator haben Sie jetzt die Wahl, welche Apps sie in das Teams-Panels-Gerät Ihrer Organisation einblenden und Berechtigungen über das Teams Admin Center anpassen.

Sie können jetzt die Teams-Apps in Teams-Panels verwenden und die Benutzeroberfläche an die Anforderungen Ihrer Organisation anpassen. Sie können entscheiden, auf welche Web-App Ihre Benutzer zugreifen und die App-Ansichten verwenden und priorisieren können. Einige Optionen, z. B. bot- und messaging-Funktionen, werden derzeit nicht unterstützt. Erfahren Sie mehr über die Teams und wie Sie Ihre Geräte in ihrer Microsoft Teams.

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Verwalten von Apps auf Teams in Teams Admin Center

**Hinweis:** Sie müssen ein globaler Administrator oder ein Teams-Dienstadministrator sein, um auf Teams Admin Center zugreifen zu können.

Endbenutzer können Apps auf einem Teams anzeigen Teams installieren. Als Administrator können Sie alle Ihre Teams für Ihre Organisation über das Teams Admin Center anzeigen und verwalten. Weitere Informationen dazu, wie Sie Ihre Apps im Admin Center Microsoft Teams verwalten, finden Sie auf der Seite **"Apps verwalten".** Auf **der Seite Apps** verwalten im Teams Admin Center können Sie auch benutzerdefinierte Apps [hochladen.](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

Nach dem Einrichten von Apps können [](/teams-app-setup-policies) Sie [App-Berechtigungsrichtlinien](/teams-app-permission-policies) und Richtlinien für die App-Einrichtung verwenden, um die App-Benutzererfahrung für bestimmte Raumkonten in Ihrer Organisation zu konfigurieren.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Anheften von Apps an Teams Panels mit Richtlinien für die App-Einrichtung

Da Teams die Möglichkeit bietet, eine Vielzahl von Apps anzuzeigen, können Administratoren entscheiden, welche Apps für die Organisation am  wichtigsten sind, und nur diese für den Startbildschirm der Teams-Panels anheften, um schnell darauf zugreifen zu können. Wenn mehr als fünf angeheftet Apps oder nicht angeheftet Apps verfügbar sind, werden sie unter dem Bildschirm **Mehr** angezeigt. Microsoft empfiehlt das Erstellen einer benutzerdefinierten App-Setuprichtlinie speziell für Teams Panels.

![Screenshot der Benutzeroberfläche der Seite mit den Richtlinien für die App-Einrichtung](media/appsetup1.png) 

Zum Verwalten von angeheftet Apps, die in den Teams-Panels angezeigt werden, melden Sie sich beim Teams Admin Center für Ihre Organisation an, und navigieren Sie zu Den Setuprichtlinien für **Teams-Apps** Auswählen oder Erstellen einer neuen Richtlinie Angeheftet \>  \>  \> Apps.

![Screenshot des Abschnitts "Angeheftet Apps" auf der Benutzeroberfläche](media/appsetup2.png) 

Microsoft empfiehlt Ihnen, Hochladen **Benutzerdefinierte** Apps zu deaktivieren und Das **Anheften** von Benutzern zu ermöglichen, um die bestmögliche Benutzererfahrung Teams App auf ihren Teams zu erhalten.

Weitere Informationen zum Anheften von Apps finden Sie unter [Verwalten von Richtlinien für die App-Einrichtung.](/teams-app-setup-policies)

## <a name="manage-apps-display-order-in-teams-panels"></a>Verwalten der Anzeigereihenfolge von Apps in Teams Panels 

![Screenshot des Abschnitts "Apps" auf der Benutzeroberfläche](media/appsetup3.png) 

Um die Reihenfolge zu verwalten, in der Apps in den Teams-Panels angezeigt werden, melden Sie sich beim Teams Admin Center für Ihre Organisation an, und navigieren Sie zu Richtlinien für die Einrichtung von **Teams-Apps** Wählen Sie die Richtlinie \>  \>  \> **Angeheftet Apps:** **Nach oben/unten** aus.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Zuweisen von Setuprichtlinien zu einem Raumressourcenkonto

Nach dem Erstellen der Setuprichtlinie muss der Administrator diese Richtlinie dem Konto für Raumressourcen zuweisen, das bei den Gruppenpanels Teams wird. Weitere Informationen finden Sie unter [Zuweisen von Richtlinien zu Benutzern und Gruppen.](/assign-policies-users-and-groups)

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Wie lange dauert es, bis Teams-Panels die neuen oder aktualisierten Richtlinien für das App-Setup erhalten?

Nach dem Bearbeiten oder Zuweisen neuer Richtlinien im Teams Admin Center kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden. Administratoren können versuchen, sich über den Bereich ab- oder abmelden, auf das  **Symbol Einstellungen** tippen und zum Startbildschirm zurück wechseln, um zu versuchen, die Richtlinien zu aktualisieren.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Wie ordnen sich die Apps auf dem Bildschirm "Mehr" an?

Auf der **Seite** Weitere Apps werden die angeheftet Apps zuerst angezeigt. Dann werden alle anderen installierten Apps in alphabetischer Reihenfolge angezeigt.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Warum werden Bot-Apps nicht in Teams angezeigt?

Derzeit werden nur statische Registerkarten-Webinhalte unterstützt.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Warum werden systemeigene Teams, z. B. Kalender und Aufgaben, nicht in Teams angezeigt?

Native Teams-Apps, z. B. Kalender und Aufgaben, werden in den Teams angezeigt.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Was ist Teams im Admin Center unter dem Abschnitt Setuprichtlinien der Unterschied zwischen installierten und angeheftet Apps?

Für Teams-Panels empfiehlt Microsoft die Verwendung angehefteter Apps, damit der Administrator die gewünschte App auswählen und ihre Anordnung ändern kann.

**Hinweis:** Einige Apps unterstützen das Anheften von Apps nicht. Wenden Sie sich an den App-Entwickler, um die Funktion zum Anheften von Apps zu aktivieren.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Warum werden andere Apps im Bildschirm "Mehr" angezeigt, obwohl sie nicht Teil der installierten oder angeheftet Apps im Abschnitt Teams-App-Setuprichtlinie sind?

Wenn Apps zuvor über andere App-Richtlinien oder manuell in den Teams-Desktop-/Webclients für das in Teams-Panels verwendete Raumressourcenkonto installiert wurden, muss sich der Administrator möglicherweise beim Raumressourcenkonto in Teams anmelden und die Apps manuell deinstallieren, indem er mit der rechten Maustaste auf die App klickt und dann Deinstallieren aus **wählt.**

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich im Bereich "Angeheftet Apps hinzufügen" keine App finden?

Nicht alle Apps können über eine App-Teams an die App angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um apps zu finden, die angeheftet werden können, suchen Sie im Bereich **Angeheftet** Apps hinzufügen nach der App. Weitere Informationen finden Sie unter Häufig gestellte Fragen [unter Arbeiten mit Richtlinien für das Einrichten von Apps.](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>Warum wird im Bereich "Setuprichtlinien" das Popup "Benutzer anheften zulassen" angezeigt, nachdem ich "Anheften von Benutzern zulassen?" deaktiviert habe

![Screenshot des Abschnitts "Setuprichtlinie" auf der Benutzeroberfläche mit einem Popupfenster, in dem bestätigt wird, dass das Anheften von Benutzern aktiv ist.](media/appsetup4.png) 

Dieses Verhalten wird für ein Gerät an einem gemeinsam genutzten Bereich erwartet und hilft, unbeabsichtigtes Anheften von Apps zu verhindern.
