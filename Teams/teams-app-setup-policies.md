---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Richtlinien für die App-Einrichtung in Microsoft Teams Benutzer in Ihrer Organisation verwenden und verwalten.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4942ae39b8ca5d067bd5b98ad2780cd0db78422d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844948"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

Als Administrator können Sie App-Setuprichtlinien verwenden, um Apps zu installieren und anheften, um die am häufigsten verwendeten Apps in Ihrer Organisation zu bewerben, und um zu entscheiden, ob Benutzer benutzerdefinierte Apps auf Ihre App Teams.

- Anheften von **Apps:** Mit App-Setuprichtlinien können Sie Apps zum Anheften auswählen, die Reihenfolge festlegen, in der sie für Ihre Benutzer angezeigt werden, und steuern, ob Benutzer ihre eigenen Apps an die App-Leiste Teams anheften können. Weitere Informationen finden Sie unter [Anheften von Apps.](#pin-apps)
- **Installieren von Apps: Mit** Richtlinien für das Einrichten von Apps können Sie Apps im Namen von Benutzern installieren, wenn diese Teams und während Besprechungen starten. Weitere Informationen finden Sie unter Installieren [von Apps.](#install-apps)
- **Hochladen Benutzerdefinierte Apps: Mit** Richtlinien für das Einrichten von Apps können Sie Benutzern das Hochladen benutzerdefinierter Apps auf Teams. Weitere Informationen finden Sie unter [Hochladen benutzerdefinierten Apps.](#upload-custom-apps)

## <a name="pin-apps"></a>Anheften von Apps

Mit dem Anheften von Apps können Sie Apps präsentieren, die Benutzer in Ihrer Organisation benötigen, einschließlich Apps, die von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt wurden.

Mit einer App-Setuprichtlinie können Sie die folgenden Aufgaben ausführen:

- Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Sie wählen die Apps aus, die Sie anheften möchten, und legen die Reihenfolge fest, in der sie angezeigt werden.
- Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.

Apps werden an die App-Leiste angeheftet. Dabei handelt es sich um die Leiste an der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients (iOS und Android).

|Microsoft Teams-Desktopclient  |Mobile Microsoft Teams-Clients |
|---------|---------|
|![Der Teams-Desktopclient.](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Der Teams-Client](media/mobile-app-ui.png)      |

> [!NOTE]
> Wenn Sie über Teams für Education verfügen, ist es wichtig zu wissen, dass die Aufgaben-App in der globalen Richtlinie standardmäßig angeheftet ist, obwohl sie derzeit nicht in der globalen Richtlinie aufgeführt ist. Dies ist die vierte App in der Liste der angeheftet Apps auf Teams Clients.

Gehen Sie wie folgt vor, um eine App-Setuprichtlinie zum Anheften von Apps zu erstellen:

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **Teams**  >  **Apps**.

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

4. Aktivieren oder deaktivieren Sie Das Anheften von Benutzern zulassen **,** je nachdem, ob Sie Benutzern das Personalisieren ihrer App-Leiste durch Anheften von Apps ermöglichen möchten.

   > [!NOTE]
   > Die  Einstellung Benutzer anheften zulassen steht im Teams Admin Center in Microsoft 365 Government Community Cloud-Umgebungen (GCC) (GCC, GCC High und DoD) zur Verfügung, hat aber aktuell keine Auswirkung.

5. Wählen **Sie unter Angeheftet Apps** die Option Apps hinzufügen **aus.**

6. Suchen Sie **im Bereich Angeheftet Apps hinzufügen** nach den Apps, die Sie hinzufügen möchten, und wählen Sie dann Hinzufügen **aus.** Sie können Apps auch nach der App-Berechtigungsrichtlinie filtern.

7. Klicken Sie auf **Hinzufügen**.

8. Ordnen Sie die Apps in der Reihenfolge an, in der sie in der App angezeigt Teams.

   ![im Abschnitt "Angeheftet Apps".](media/app-setup-policies-new-policy-setup.png)

9. Klicken Sie auf **Speichern**.

## <a name="install-apps"></a>Installieren von Apps

Sie können auswählen, welche Apps standardmäßig für Benutzer in ihrer persönlichen [](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)Teams-Umgebung installiert werden, Apps als Messagingerweiterungen installieren und Apps für die Installation in Besprechungen festlegen.

Mit einer App-Setuprichtlinie können Sie die folgenden Aufgaben ausführen:

- Installieren von Apps für Benutzer in ihrer persönlichen Teams Umgebung
- Installieren von Apps für Benutzer als Messaging-Erweiterungen
- Installieren von Apps in Besprechungen für Besprechungsorganisatoren

> [!NOTE]
> Benutzer können Apps weiterhin [](teams-app-permission-policies.md) selbst installieren, wenn die Ihnen zugewiesene App-Berechtigungsrichtlinie dies zulässt.

Gehen Sie wie folgt vor, um eine App-Setuprichtlinie zum Installieren von Apps zu erstellen:

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **Teams**  >  **Apps**.

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

4. Wählen **Sie unter Installierte** Apps die **Option Apps hinzufügen aus.**

5. Suchen Sie **im Bereich Installierte Apps** hinzufügen nach den Apps, die Sie automatisch für Benutzer installieren möchten. Sie können Apps auch nach der App-Berechtigungsrichtlinie filtern.

6. Klicken Sie auf **Hinzufügen**.

![App-Richtlinie installieren.](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> Benutzer können keine Apps deinstallieren, die von Administratoren installiert wurden.

## <a name="upload-custom-apps"></a>Hochladen von benutzerdefinierten Apps

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen, die Benutzern das Hochladen benutzerdefinierter Apps auf Teams.

Gehen Sie wie folgt vor, um eine App-Setuprichtlinie zu erstellen, mit der Benutzer benutzerdefinierte Apps Teams App hochladen können:

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **Teams**  >  **Apps**.

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

4. Aktivieren oder deaktivieren Sie **Hochladen Apps,** je nachdem, ob Sie Benutzern das Hochladen benutzerdefinierter Apps auf ihren Teams.

> [!NOTE]
> Sie können diese Einstellung nicht ändern, wenn **Drittanbieter-Apps zulassen** in [den organisationsweiten App-Einstellungen deaktiviert ist.](manage-apps.md#manage-org-wide-app-settings)

## <a name="manage-app-setup-policies"></a>Verwalten von Richtlinien für die App-Einrichtung

Sie verwalten App-Setuprichtlinien im Microsoft Teams Admin Center. Verwenden Sie die globale (organisationsweite Standardrichtlinie) oder erstellen und weisen Sie benutzerdefinierte Richtlinien zu.  Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie bearbeiten die Einstellungen in der globalen Richtlinie so, dass sie die von Ihnen verwendeten Apps enthalten. Wenn Sie Teams Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen sie eine oder mehrere benutzerdefinierte Richtlinien, und weisen Sie sie zu.

![auf der Seite App-Setuprichtlinien.](media/app-setup-policies.png)

### <a name="edit-an-app-setup-policy"></a>Bearbeiten einer App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen (organisationsweiten Standard)-Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **Teams**  >  **Apps**.

2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten aus.**

3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor.

4. Klicken Sie auf **Speichern**.

### <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern

Weitere Informationen zum Zuweisen von Richtlinien zu Benutzern finden Sie unter Zuweisen von Richtlinien [zu Benutzern und Gruppen.](assign-policies-users-and-groups.md)

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit Richtlinien für die App-Einrichtung

#### <a name="can-i-assign-an-app-setup-policy-to-a-group"></a>Kann ich einer Gruppe eine App-Setuprichtlinie zuweisen?

App-Setuprichtlinien können mithilfe von PowerShell Gruppen zugewiesen werden. Weitere Informationen zum Zuweisen von Richtlinien zu Gruppen mithilfe von PowerShell finden Sie unter Zuweisen von Richtlinien [zu Benutzern und Gruppen.](assign-policies-users-and-groups.md#use-the-powershell-option)

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten Richtlinien für die App-Einrichtung sind im Microsoft Teams Admin Center enthalten?

- **Global (Organisationsweite Standardeinstellung):** Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um die Apps anheften, die für Ihre Benutzer am wichtigsten sind.

- **FrontlineWorker:** Diese Richtlinie gilt für Frontline Workers. Sie können sie Mitarbeitern in Frontline in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie von Ihnen erstellte benutzerdefinierte Richtlinien benutzern die Richtlinie zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt Zuweisen einer benutzerdefinierten [App-Setuprichtlinie](#assign-a-custom-app-setup-policy-to-users) zu Benutzern in diesem Artikel.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich im Bereich "Angeheftet Apps hinzufügen" keine App finden?

Nicht alle Apps können über eine App-Teams an die App angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um apps zu finden, die angeheftet werden können, suchen Sie im Bereich **Angeheftet** Apps hinzufügen nach der App. Registerkarten mit einem persönlichen Bereich (statische **Registerkarten)** und Bots können an den Teams-Desktopclient angeheftet werden, und diese Apps sind im Bereich "Angeheftet Apps hinzufügen" verfügbar.

Beachten Sie, dass im Teams App Store alle Teams aufgeführt sind. Der **Bereich Angeheftet Apps hinzufügen enthält** nur Apps, die über eine Richtlinie Teams angeheftet werden können.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin Teams für Education Administrator. Was muss ich über Richtlinien für das App-Setup in ihrem Teams für Education

Die Calling-App ist in der App Teams für Education. Wenn Sie eine neue benutzerdefinierte App-Setuprichtlinie erstellen, wird die Aufrufende App in der Liste der Apps angezeigt. Die App ist jedoch nicht an Clients Teams angeheftet, und Teams für Education Benutzer sehen die Anrufe-App nicht in Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Wie viele angeheftet Apps können einer Richtlinie hinzugefügt werden?

Mindestens zwei Apps müssen an die mobilen Teams (iOS und Android) angeheftet werden. Wenn eine Richtlinie weniger als zwei Apps hat, entsprechen die mobilen Clients nicht den Richtlinieneinstellungen und verwenden stattdessen weiterhin die vorhandene Konfiguration.

Die Anzahl der angeheftet Apps, die Sie einer Richtlinie hinzufügen können, ist nicht begrenzt.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden?

Nach Bearbeiten oder Zuweisen einer Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle ihre angeheftet Apps in Teams

Um alle Apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen Benutzer je nach Anzahl der installierten Apps und Größe des Teams-Clientfensters möglicherweise die folgenden Schritte tun.

|Microsoft Teams-Desktopclient |Mobile Microsoft Teams-Clients |
|---------|---------|
|Wählen Sie auf der App-Leiste Teams **aus, ... Weitere Apps**.| Wischen Sie in der App-Leiste Teams Unteren Bildschirmrand nach oben.|
|![Weitere Apps im Teams-Desktopclients.](media/app-setup-policies-desktop-more-apps.png)<br>   |![Weitere Apps im mobilen Teams-Client](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die mobile Teams wissen?

Die Teams mobilen Clients (iOS und Android) unterstützen persönliche Apps mit statischen Registerkarten. Apps, die an den Teams-Desktopclient angeheftet sind, werden im Teams Clients angezeigt. Persönliche Bots werden in Chat auf mobilen Clients angezeigt.

Apps von Drittanbietern (die über Apps heruntergeladen Teams Store können) müssen genehmigt werden, bevor sie auf mobilen Geräten angezeigt werden. Wenn ein Administrator eine App anheftet, die von Microsoft für Mobile nicht genehmigt wurde, wird sie auf dem Teams-Desktop, aber nicht auf Mobilgeräten angezeigt. Weitere [Informationen finden Sie unter Mobile](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) Clients.

Bei den mobilen Teams-Clients sehen die Benutzer Kern-Teams-Apps wie Aktivität, Chat und Teams, und Sie können einige Erstanbieter-Apps von Microsoft anheften, z. B. Schichten.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge von Apps ändern, die über eine Richtlinie angeheftet sind

Benutzer können die Reihenfolge ihrer angeheftet Apps auf desktop Teams und **mobilen** Clients ändern, wenn die Option Benutzer-Anheften zulassen aktiviert ist. Benutzer können die Reihenfolge ihrer angeheftet Apps auf ihren Webclients Teams ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften von Benutzern Vorrang?

Administratorkontakte haben immer Vorrang. Wenn die **Option Anheften von** Benutzern zulassen aktiviert ist, behalten Benutzer ihre angeheftet Apps unterhalb der von Administratoren angeheftet Apps. Wenn die **Option** Benutzer anheften zulassen deaktiviert ist, verlieren Benutzer ihre bereits vorhandenen Pins, und nur von Administratoren angeheftierte Apps werden in der App-Leiste angezeigt.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-Apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und veröffentlicht, entweder in AppSource oder im Mandanten-App-Katalog, aber das App-Symbol wird nicht wie erwartet angezeigt, wenn die App an die App-Leiste in Der App Teams angeheftet ist. Wie behebt ich das Problem?

Stellen Sie sicher, dass Sie die Logorichtlinien einhalten, bevor Sie die App einreichen. Weitere Informationen finden Sie unter [Prüfliste für die Übermittlung des Verkäufer-Dashboards.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies-users-and-groups.md)
