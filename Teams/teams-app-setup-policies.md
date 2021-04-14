---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinien zum Einrichten von Apps in Microsoft Teams für Benutzer in Ihrer Organisation verwenden und verwalten.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ee50af6dec780480b8efdbf39dabb8e52ff03f3a
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697710"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

Als Administrator können Sie die folgenden Aufgaben mithilfe von App-Setuprichtlinien ausführen:

- Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Sie wählen die apps aus, die angeheften werden sollen, und legen die Reihenfolge fest, in der sie angezeigt werden. Durch das Anheften von Apps können Sie Apps präsentieren, die Benutzer in Ihrer Organisation benötigen, einschließlich Apps, die von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt wurden.
- Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.
- Installieren Sie Apps im Auftrag von Benutzern. Sie wählen aus, welche Apps standardmäßig für Benutzer installiert werden, wenn sie Teams starten. Beachten Sie, dass Benutzer Apps weiterhin [](teams-app-permission-policies.md) selbst installieren können, wenn die ihnen zugewiesene App-Berechtigungsrichtlinie dies zulässt.

> [!Note]
> Bei apps installed by admins, users can't uninstall those apps.

Apps werden an die App-Leiste angeheftet, die die Leiste auf der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients (iOS und Android) ist.

|Desktopclient für Teams  |Mobile Microsoft Teams-Clients |
|---------|---------|
|![Der Desktopclient von Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Der mobile Teamclient](media/mobile-app-ui.png)      |

Um die von Administratoren installierten Apps zu sehen, wählen Die Benutzer in der App-Leiste **... aus. Weitere Apps** in den Desktop- und Webclients von Teams, und wischen Sie in den mobilen Clients nach oben.

Sie verwalten Die Richtlinien für das Einrichten von Apps im Microsoft Teams Admin Center. Verwenden Sie die globale (organisationsweite Standardrichtlinie) oder erstellen und weisen Sie benutzerdefinierte Richtlinien zu.  Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie bearbeiten die Einstellungen in der globalen Richtlinie so, dass sie die apps enthalten, die Sie wünschen. Wenn Sie Teams für verschiedene Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen und weisen Sie eine oder mehrere benutzerdefinierte Richtlinien zu.

![Seite "App-Setuprichtlinien"](media/app-setup-policies.png)

> [!NOTE]
> Wenn Sie über Teams for Education verfügen, ist es wichtig zu wissen, dass die Aufgaben-App standardmäßig in der globalen Richtlinie angeheftet ist, obwohl sie derzeit nicht in der globalen Richtlinie aufgeführt wird. Es ist die vierte App in der Liste der angeheftet Apps auf Teams-Clients.

## <a name="create-a-custom-app-setup-policy"></a>Erstellen einer benutzerdefinierten App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Setuprichtlinien für Teams-Apps.**  >  

2. Klicken Sie auf **Hinzufügen**.

   ![Seite "App-Setuprichtlinien hinzufügen"](media/app-setup-policies-add.png)

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

4. Aktivieren oder deaktivieren Sie benutzerdefinierte Apps **hochladen,** je nachdem, ob Sie benutzern das Hochladen benutzerdefinierter Apps in Teams ermöglichen möchten. Sie können diese Einstellung nicht **ändern,** wenn Apps von Drittanbietern zulassen in [organisationsweiten App-Einstellungen deaktiviert ist.](manage-apps.md#manage-org-wide-app-settings)

5. Aktivieren oder deaktivieren Sie Benutzer **anheften** zulassen , je nachdem, ob Sie benutzern das Personalisieren ihrer App-Leiste durch Anheften von Apps ermöglichen möchten.

   > [!NOTE]
   > Die **Einstellung** Benutzer anheften zulassen ist im Teams Admin Center in Microsoft 365 Government Community Cloud (GCC)-Umgebungen (GCC, GCC High und DoD) verfügbar, hat aber derzeit keine Auswirkung.

6. Gehen Sie wie folgt vor, um Apps für Benutzer zu installieren:

    1. Wählen **Sie unter Installierte Apps** die Option Apps hinzufügen **aus.**

    2. Suchen Sie **im Bereich** Installierte Apps hinzufügen nach den Apps, die Sie beim Starten von Teams automatisch installieren möchten. Sie können Apps auch nach App-Berechtigungsrichtlinie filtern. Wenn Sie Ihre Liste der Apps ausgewählt haben, wählen Sie **Hinzufügen aus.**

       ![Bereich "Installierte Apps hinzufügen"](media/app-setup-policies-add-installed-apps.png)

7. Zum Anheften von Apps gehen Sie wie folgt vor:

    1. Wählen **Sie unter Angeheftet Apps** die Option Apps hinzufügen **aus.**

    2. Suchen Sie **im Bereich Angeheftet Apps** hinzufügen nach den Apps, die Sie hinzufügen möchten, und wählen Sie dann Hinzufügen **aus.** Sie können Apps auch nach App-Berechtigungsrichtlinie filtern. Wenn Sie Ihre Liste der anheftende Apps ausgewählt haben, wählen Sie **Hinzufügen aus.**

       ![Bereich "Angeheftet hinzufügen"](media/app-setup-policies-add-apps.png)

    3. Ordnen Sie die Apps in der Reihenfolge an, in der sie in Teams angezeigt werden sollen, und wählen Sie dann **Speichern aus.**

       ![Abschnitt "Angeheftet"](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Bearbeiten einer App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen (organisationsweiten Standardrichtlinie) und benutzerdefinierten Richtlinien, die Sie erstellen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Setuprichtlinien für Teams-Apps.**  >  

2. Wählen Sie die Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken, und wählen Sie dann **Bearbeiten** aus.

3. Nehmen Sie nun die gewünschten Änderungen vor.

4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit Richtlinien für die App-Einrichtung

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten Richtlinien für das Einrichten von Apps sind im Microsoft Teams Admin Center enthalten?

- **Global (Organisationsweite Standardeinstellung):** Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um Apps anheften, die für Ihre Benutzer am wichtigsten sind.

- **FrontlineWorker:** Diese Richtlinie gilt für Frontline-Mitarbeiter. Sie können sie Den Frontline-Mitarbeitern in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie von Ihnen erstellte benutzerdefinierte Richtlinien den Benutzern die Richtlinie zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt Zuweisen einer benutzerdefinierten [App-Setuprichtlinie](#assign-a-custom-app-setup-policy-to-users) zu Benutzern in diesem Artikel.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich im Bereich "Angeheftet Apps hinzufügen" keine App finden?

Nicht alle Apps können über eine App-Setuprichtlinie an Teams angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Wenn Sie Apps suchen möchten, die angeheftet werden können, suchen Sie im Bereich Angeheftet Apps **hinzufügen nach der** App. Registerkarten, die einen persönlichen Bereich (statische **Registerkarten)** und Bots haben, können an den Desktopclient von Teams angeheftet werden, und diese Apps sind im Bereich Angeheftet Apps hinzufügen verfügbar.

Denken Sie daran, dass im Teams App Store alle Teams-Apps aufgeführt sind. Der **Bereich Angeheftet Apps hinzufügen** enthält nur Apps, die über eine Richtlinie an Teams angeheftet werden können.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein Teams for Education-Administrator. Was muss ich über Richtlinien zum Einrichten von Apps in Teams for Education wissen?

Die Anruf-App ist in Teams for Education nicht verfügbar. Wenn Sie eine neue benutzerdefinierte App-Setuprichtlinie erstellen, wird die Aufrufende App in der Liste der Apps angezeigt. Die App ist jedoch nicht an Teams-Clients angeheftet, und Teams for Education-Benutzer sehen die Anruf-App in Teams nicht.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Wie viele angeheftet Apps können einer Richtlinie hinzugefügt werden?

Mindestens zwei Apps müssen an die mobilen Teams-Clients (iOS und Android) angeheftet werden. Wenn eine Richtlinie weniger als zwei Apps hat, entsprechen die mobilen Clients nicht den Richtlinieneinstellungen und verwenden stattdessen weiterhin die vorhandene Konfiguration.

Die Anzahl der angeheftet Apps, die Sie einer Richtlinie hinzufügen können, ist nicht begrenzt.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden

Nach Bearbeiten oder Zuweisen einer Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle ihre angeheftet Apps in Teams sehen?

Um alle Apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen Die Benutzer möglicherweise die folgenden Schritte je nach Anzahl der installierten Apps und der Größe ihres Teams-Clientfensters tun.

|Desktopclient für Teams |Mobile Microsoft Teams-Clients |
|---------|---------|
|Wählen Sie in der App-Leiste auf der Seite von Teams **... aus. Weitere Apps**.| Wischen Sie in der App-Leiste am unteren Rand von Teams nach oben.|
|![Weitere Apps im Teams-Desktopclient](media/app-setup-policies-desktop-more-apps.png)<br>   |![Weitere Apps im mobilen Teamclient](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die mobile Benutzererfahrung von Teams wissen?

Die mobilen Teams-Clients (iOS und Android) unterstützen derzeit keine persönlichen Apps mit statischen Registerkarten. Je nach den in der Richtlinie festgelegten Apps werden apps, die an den Desktopclient von Teams angeheftet sind, möglicherweise nicht in den mobilen Teams-Clients angezeigt. Persönliche Bots werden weiterhin in Chat auf mobilen Clients angezeigt.

Bei den mobilen Teams-Clients werden den Benutzern kernige Teams-Apps wie Aktivität, Chat und Teams angezeigt, und Sie können einige Apps von Microsoft erster Partei anheften, z. B. Schichten.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge der apps ändern, die über eine Richtlinie angeheftet wurden

Benutzer können die Reihenfolge ihrer angeheftet Apps auf Desktop- und mobilen Teams-Clients ändern, wenn die Option Benutzer **anheften** zulassen aktiviert ist. Benutzer können die Reihenfolge ihrer angeheftet Apps auf Teams-Webclients nicht ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften von Benutzern Vorrang

Administratorpins haben immer Vorrang. Wenn die **Option Benutzer anheften** zulassen aktiviert ist, behalten die Benutzer ihre angeheftet Apps unterhalb von vom Administrator angeheftet apps bei. Wenn die Option Benutzer **anheften** zulassen deaktiviert ist, gehen die bereits vorhandenen Pins verloren, und nur von Administratoren angeheftierte Apps sind in der App-Leiste vorhanden.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-Apps

Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und veröffentlicht, entweder in AppSource oder im Katalog der Mandanten-App, aber das App-Symbol wird nicht wie erwartet angezeigt, wenn die App an die App-Leiste in Teams angeheftet wird. Wie kann ich die Lösung beheben?

Achten Sie darauf, dass Sie die Logorichtlinien einhalten, bevor Sie die App übermitteln. Weitere Informationen finden Sie unter [Checkliste für die Übermittlung des Verkäuferdashboards.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
