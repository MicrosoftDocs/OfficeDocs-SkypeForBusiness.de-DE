---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie App-Setuprichtlinien in Microsoft Teams für Benutzer in Ihrer Organisation verwenden und verwalten.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 7c00a5e70684a93f31a11d48ac542920fca3b697
ms.sourcegitcommit: 9f7372f7568b4275169590510d2b7a0c0ad7577b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2022
ms.locfileid: "65171731"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

Als Administrator können Sie App-Setuprichtlinien verwenden, um Apps zu installieren und anzuheften, um die am häufigsten verwendeten Apps in Ihrer Organisation zu bewerben, und entscheiden, ob Benutzer benutzerdefinierte Apps in Teams hochladen möchten.

- **Apps anheften:** Mit App-Setuprichtlinien können Sie Apps auswählen, die angeheftet werden sollen, die Reihenfolge festlegen, in der sie für Ihre Benutzer in der Teams App-Leiste oder im Bereich zum Verfassen von Nachrichten angezeigt werden, und steuern, ob Benutzer ihre eigenen Apps anheften können. Weitere Informationen finden Sie unter ["Apps anheften](#pin-apps)".
- **Installieren von Apps:** Mit App-Setuprichtlinien können Sie Apps im Namen von Benutzern installieren, wenn sie Teams und während Besprechungen starten. Weitere Informationen finden [Sie unter "Installieren von Apps"](#install-apps).
- **Hochladen benutzerdefinierten Apps:** Mit App-Setuprichtlinien können Benutzer benutzerdefinierte Apps in Teams hochladen. Weitere Informationen finden Sie [unter Hochladen benutzerdefinierten Apps](#upload-custom-apps).

## <a name="pin-apps"></a>Apps anheften

> [!NOTE]
> Für die Mitarbeiter in Service und Produktion in Ihrer Organisation empfehlen wir die Verwendung der maßgeschneiderten App-Erfahrung in Service und Produktion. Dieses Feature heftt die relevantesten Apps in Teams für Benutzer an, die über eine [F-Lizenz](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt) verfügen. Weitere Informationen finden Sie unter ["Anpassen Teams Apps für Mitarbeiter in Service und Produktion](pin-teams-apps-based-on-license.md)".

Durch das Anheften von Apps können Sie Apps präsentieren, die Benutzer in Ihrer Organisation benötigen, einschließlich Apps, die von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt wurden.

Mithilfe einer App-Setuprichtlinie können Sie die folgenden Aufgaben ausführen:

- Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Sie wählen die Apps aus, die angeheftet werden sollen, und legen die Reihenfolge fest, in der sie angezeigt werden.
- Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.

Apps werden an die App-Leiste angeheftet. Dies ist die Leiste auf der linken Seite des Teams Desktopclients und am unteren Rand der Teams mobilen Clients (iOS und Android).

|Microsoft Teams-Desktopclient  |Mobile Microsoft Teams-Clients |
|---------|---------|
|![Der Teams Desktopclient.](media/app-setup-policies-desktop-app-bar.png).  |   ![Der Teams mobile Client](media/mobile-app-ui.png)      |

Die Messaging-Erweiterungen sind unten im Nachrichtenbereich zum Verfassen verfügbar.

> [!NOTE]
> Wenn Sie Teams für Education haben, ist es wichtig zu wissen, dass die Aufgaben-App standardmäßig in der globalen Richtlinie angeheftet ist, obwohl sie derzeit nicht in der globalen Richtlinie aufgeführt ist.

Führen Sie die folgenden Schritte aus, um eine App-Setuprichtlinie zum Anheften von Apps zu erstellen:

1. Melden Sie sich beim [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) an.

1. Wechseln Sie im linken Bereich zu **Teams** **AppsSetup-Richtlinien** > .

1. Klicken Sie auf **Hinzufügen**.

1. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

1. Aktivieren Sie **die Benutzer-Anheftung**.

   > [!NOTE]
   > Die Einstellung zum **Anheften von Benutzern** ist im Teams Admin Center in Microsoft 365 Government Community Cloud (GCC)-Umgebungen (GCC, GCC High und DoD) verfügbar, hat aber derzeit keine Auswirkungen.

1. Wählen Sie unter **"Angeheftete Apps**" die Option **"Apps hinzufügen"** aus.

1. Suchen Sie im Bereich **"Angeheftete Apps hinzufügen** " nach den Apps, die Sie hinzufügen möchten, und wählen Sie dann **"Hinzufügen"** aus. Sie können Apps auch nach App-Berechtigungsrichtlinie filtern.

1. Klicken Sie auf **Hinzufügen**.

1. Ordnen Sie die Apps unter der **App-Leiste** oder **Messaging-Erweiterungen** in der Reihenfolge an, in der sie in Teams angezeigt werden sollen.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Abschnitt &quot;Angeheftete Apps&quot;"border="true":::

1. Klicken Sie auf **Speichern**.

## <a name="install-apps"></a>Installieren von Apps

Sie können auswählen, welche Apps standardmäßig für Benutzer in ihrer persönlichen Teams-Umgebung installiert werden, Apps als [Messaging-Erweiterungen](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions) installieren und Apps für die Installation in Besprechungen festlegen.

Mithilfe einer App-Setuprichtlinie können Sie die folgenden Aufgaben ausführen:

- Installieren von Apps für Benutzer in ihrer persönlichen Teams-Umgebung
- Installieren von Apps für Benutzer als Messaging-Erweiterungen
- Installieren von Apps in Besprechungen für Besprechungsorganisatoren

> [!NOTE]
> Benutzer können Apps weiterhin selbst installieren, wenn die Ihnen zugewiesene [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) dies zulässt.

Führen Sie die folgenden Schritte aus, um eine App-Setuprichtlinie zum Installieren von Apps zu erstellen:

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams** **AppsSetup-Richtlinien** > .

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

4. Wählen Sie unter **"Installierte Apps**" die Option **"Apps hinzufügen"** aus.

5. Suchen Sie im Bereich " **Installierte Apps hinzufügen** " nach den Apps, die Sie automatisch für Benutzer installieren möchten. Sie können Apps auch nach App-Berechtigungsrichtlinie filtern.

6. Klicken Sie auf **Hinzufügen**.

![Installieren Sie die App-Richtlinie.](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> Benutzer können keine Apps deinstallieren, die von Administratoren installiert wurden.

## <a name="upload-custom-apps"></a>Hochladen benutzerdefinierter Apps

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen, mit der Benutzer benutzerdefinierte Apps in Teams hochladen können.

Führen Sie die folgenden Schritte aus, um eine App-Setuprichtlinie zu erstellen, mit der Benutzer benutzerdefinierte Apps in Teams hochladen können:

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams** **AppsSetup-Richtlinien** > .

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

4. Aktivieren oder deaktivieren Sie **Hochladen benutzerdefinierten Apps**, je nachdem, ob Benutzer benutzerdefinierte Apps in Teams hochladen möchten.

> [!NOTE]
> Sie können diese Einstellung nicht ändern, wenn **Apps von Drittanbietern** in [organisationsweiten App-Einstellungen](manage-apps.md#manage-org-wide-app-settings) deaktiviert sind.

## <a name="manage-app-setup-policies"></a>Verwalten von App-Setuprichtlinien

Sie verwalten App-Setuprichtlinien im Microsoft Teams Admin Center. Verwenden Sie die globale Richtlinie (organisationsweite Standardrichtlinie), oder erstellen und weisen Sie benutzerdefinierte Richtlinien zu.  Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie bearbeiten die Einstellungen in der globalen Richtlinie, um die gewünschten Apps einzuschließen. Um Teams für verschiedene Benutzergruppen in Ihrer Organisation anzupassen, erstellen und weisen Sie eine oder mehrere benutzerdefinierte Richtlinien zu.

![auf der Seite "App-Setuprichtlinien".](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>Bearbeiten einer App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen Richtlinie (organisationsweite Standardrichtlinie) und benutzerdefinierter Richtlinien, die Sie erstellen.

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams** **AppsSetup-Richtlinien** > .

2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **"Bearbeiten"** aus.

3. Nehmen Sie die gewünschten Änderungen vor.

4. Klicken Sie auf **Speichern**.

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern und Gruppen

Weitere Informationen zum Zuweisen von Richtlinien zu Ihren Benutzern und Gruppen finden Sie unter [Zuweisen von Richtlinien zu Benutzern und Gruppen](assign-policies-users-and-groups.md).

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit App-Setuprichtlinien

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten App-Setuprichtlinien sind im Microsoft Teams Admin Center enthalten?

- **Global (organisationsweiter Standard):** Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um Apps anzuheften, die für Ihre Benutzer am wichtigsten sind.

- **FrontlineWorker**: Diese Richtlinie richtet sich an Mitarbeiter in Service und Produktion. Sie können es Mitarbeitern in Service und Produktion in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie benutzerdefinierte Richtlinien, die Sie erstellen, benutzern die Richtlinie zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt " [Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern](#assign-a-custom-app-setup-policy-to-users-and-groups) " in diesem Artikel.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich im Bereich "Angeheftete Apps hinzufügen" keine App finden?

Nicht alle Apps können über eine App-Setuprichtlinie an Teams angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um Apps zu finden, die angeheftet werden können, suchen Sie im Bereich " **Angeheftete Apps hinzufügen** " nach der App. Registerkarten mit einem persönlichen Bereich (statische Registerkarten) und Bots können an den Teams Desktopclient angeheftet werden. Diese Apps sind im Bereich **"Angeheftete Apps hinzufügen"** verfügbar.

Beachten Sie, dass im Teams App Store alle Teams Apps aufgeführt sind. Der Bereich **"Angeheftete Apps hinzufügen"** enthält nur Apps, die über eine Richtlinie an Teams angeheftet werden können.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein Teams für Education-Administrator. Was muss ich über App-Setuprichtlinien in Teams für Education wissen

Die Anruf-App ist in Teams für Education nicht verfügbar. Wenn Sie eine neue benutzerdefinierte App-Setuprichtlinie erstellen, wird die aufrufende App in der Liste der Apps angezeigt. Die App ist jedoch nicht an Teams Clients angeheftet, und Teams für Education Benutzer die Anruf-App in Teams nicht sehen.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Wie viele angeheftete Apps einer Richtlinie hinzugefügt werden können

Mindestens zwei Apps müssen an die Teams mobilen Clients (iOS und Android) angeheftet werden. Wenn eine Richtlinie weniger als zwei Apps hat, spiegeln die mobilen Clients nicht die Richtlinieneinstellungen wider und verwenden stattdessen weiterhin die vorhandene Konfiguration.

Die Anzahl der angehefteten Apps, die Sie einer Richtlinie hinzufügen können, ist nicht begrenzt.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden?

Nach Bearbeiten oder Zuweisen einer Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle angehefteten Apps in Teams

Um alle Apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen Benutzer je nach Anzahl der installierten Apps und größe ihres Teams Clientfensters möglicherweise Folgendes tun.

|Microsoft Teams-Desktopclient |Mobile Microsoft Teams-Clients |
|---------|---------|
|Wählen Sie in der App-Leiste auf der Seite von Teams **... Weitere Apps**.| Wischen Sie in der App-Leiste am unteren Rand der Teams nach oben.|
|![Weitere Apps im Teams Desktopclient.](media/app-setup-policies-desktop-more-apps.png)   |![weitere Apps im Teams mobilen Client](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die Teams mobile Erfahrung wissen?

Die Teams mobile Clients (iOS und Android) unterstützen persönliche Apps mit statischen Registerkarten. An den Teams Desktopclient angeheftete Apps werden in den Teams mobilen Clients angezeigt. Persönliche Bots werden im Chat auf mobilen Clients angezeigt.

Drittanbieter-Apps (die von Teams Store heruntergeladen werden können) müssen genehmigt werden, bevor sie auf mobilgeräten angezeigt werden. Wenn ein Administrator eine App anheftet, die von Microsoft für Mobile nicht genehmigt wird, wird sie auf dem Teams Desktop angezeigt, aber nicht auf mobilgeräten. Weitere Informationen finden Sie unter ["Mobile Clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) ".

Mit den Teams mobilen Clients sehen Benutzer kernige Teams-Apps wie Aktivität, Chat und Teams, und Sie können einige Erstanbieter-Apps von Microsoft anheften, z. B. Schichten.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge von Apps ändern, die über eine Richtlinie angeheftet sind

Benutzer können die Reihenfolge ihrer angehefteten Apps auf Teams Desktop- und mobilen Clients ändern, wenn die Option "**Benutzer anheften**" aktiviert ist. Benutzer können die Reihenfolge ihrer angehefteten Apps auf Teams Webclients nicht ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften von Benutzern Vorrang

Administrator-Pins haben immer Vorrang. Wenn die Option zum **Anheften von** Benutzern aktiviert ist, behalten benutzer ihre angehefteten Apps unter den vom Administrator angehefteten Apps bei. Wenn die Option zum **Anheften von** Benutzern deaktiviert ist, verlieren Benutzer ihre bereits vorhandenen Pins, und nur von Administratoren angeheftete Apps sind in der App-Leiste vorhanden.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-Apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation hat eine benutzerdefinierte Teams App erstellt und entweder in AppSource oder im Mandanten-App-Katalog veröffentlicht, aber das App-Symbol wird nicht wie erwartet angezeigt, wenn die App in Teams an die App-Leiste angeheftet ist. Gewusst wie beheben?

Stellen Sie sicher, dass Sie die Logorichtlinien befolgen, bevor Sie die App übermitteln. Weitere Informationen finden Sie unter [Checkliste für die Übermittlung an das Verkäuferdashboard](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-articles"></a>Verwandte Artikel

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies-users-and-groups.md)
