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
description: Hier erfahren Sie, wie Sie Richtlinien für die App-Einrichtung in Microsoft Teams Benutzer in Ihrer Organisation verwenden und verwalten.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059199"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

Als Administrator können Sie App-Setuprichtlinien verwenden, um die folgenden Aufgaben auszuführen:

- Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Sie wählen die Apps aus, die Sie anheften möchten, und legen die Reihenfolge fest, in der sie angezeigt werden. Mit dem Anheften von Apps können Sie Apps präsentieren, die Benutzer in Ihrer Organisation benötigen, einschließlich Apps, die von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt wurden.
- Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.
- Installieren sie Apps im Auftrag von Benutzern. Sie wählen aus, welche Apps für Benutzer standardmäßig installiert werden, wenn sie ihre Teams. Denken Sie daran, dass Benutzer Apps [](teams-app-permission-policies.md) weiterhin selbst installieren können, wenn die ihnen zugewiesene App-Berechtigungsrichtlinie dies zulässt.

> [!Note]
> Für apps, die von Administratoren installiert wurden, können Benutzer diese Apps nicht deinstallieren.

Apps werden an die App-Leiste angeheftet. Dabei handelt es sich um die Leiste an der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients (iOS und Android).

|Teams-Desktopclient  |Mobile Microsoft Teams-Clients |
|---------|---------|
|![Der Teams-Desktopclient](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Der Teams-Client](media/mobile-app-ui.png)      |

Um die von Administratoren installierten Apps zu sehen, wählen Benutzer auf der App-Leiste **... Weitere Apps** in den Teams und Webclients, und wischen Sie in den mobilen Clients nach oben.

Sie verwalten App-Setuprichtlinien im Microsoft Teams Admin Center. Verwenden Sie die globale (organisationsweite Standardrichtlinie) oder erstellen und weisen Sie benutzerdefinierte Richtlinien zu.  Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie bearbeiten die Einstellungen in der globalen Richtlinie so, dass sie die von Ihnen verwendeten Apps enthalten. Wenn Sie Teams Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen und weisen Sie eine oder mehrere benutzerdefinierte Richtlinien zu.

![Seite "App-Setuprichtlinien"](media/app-setup-policies.png)

> [!NOTE]
> Wenn Sie Teams Education haben, ist es wichtig zu wissen, dass die Aufgaben-App in der globalen Richtlinie standardmäßig angeheftet ist, obwohl sie derzeit nicht in der globalen Richtlinie aufgeführt ist. Dies ist die vierte App in der Liste der angeheftet Apps auf Teams Clients.

## <a name="create-a-custom-app-setup-policy"></a>Erstellen einer benutzerdefinierten App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **Teams**  >  **Apps.**

2. Klicken Sie auf **Hinzufügen**.

   ![Die Seite "App-Setuprichtlinien hinzufügen"](media/app-setup-policies-add.png)

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

4. Aktivieren oder deaktivieren Sie **Hochladen Apps,** je nachdem, ob Sie Benutzern das Hochladen benutzerdefinierter Apps auf ihren Teams. Sie können diese Einstellung nicht ändern, wenn **Drittanbieter-Apps zulassen** in [den organisationsweiten App-Einstellungen deaktiviert ist.](manage-apps.md#manage-org-wide-app-settings)

5. Aktivieren oder deaktivieren Sie Das Anheften von Benutzern zulassen **,** je nachdem, ob Sie Benutzern das Personalisieren ihrer App-Leiste durch Anheften von Apps ermöglichen möchten.

   > [!NOTE]
   > Die **Einstellung** Benutzer anheften zulassen steht im Teams Admin Center in Microsoft 365 Government Community Cloud-Umgebungen (GCC GCC, GCC High und DoD) zur Verfügung, hat aber aktuell keine Auswirkung.

6. Gehen Sie wie folgt vor, um Apps für Benutzer zu installieren:

    1. Wählen **Sie unter Installierte** Apps die Option **Apps hinzufügen aus.**

    2. Suchen Sie **im Bereich Installierte Apps** hinzufügen nach den Apps, die Sie automatisch installieren möchten, wenn Benutzer Teams. Sie können Apps auch nach der App-Berechtigungsrichtlinie filtern. Wenn Sie Ihre App-Liste ausgewählt haben, wählen Sie **Hinzufügen aus.**

       ![Der Bereich "Installierte Apps hinzufügen"](media/app-setup-policies-add-installed-apps.png)

7. Zum Anheften von Apps gehen Sie wie folgt vor:

    1. Wählen **Sie unter Angeheftet Apps** die Option Apps hinzufügen **aus.**

    2. Suchen Sie **im Bereich Angeheftet Apps hinzufügen** nach den Apps, die Sie hinzufügen möchten, und wählen Sie dann Hinzufügen **aus.** Sie können Apps auch nach der App-Berechtigungsrichtlinie filtern. Wenn Sie Ihre Liste der Apps zum Anheften ausgewählt haben, wählen Sie **Hinzufügen aus.**

       ![Der Bereich "Angeheftet Apps hinzufügen"](media/app-setup-policies-add-apps.png)

    3. Ordnen Sie die Apps in der Reihenfolge an, in der sie im Teams, und wählen Sie dann **Speichern aus.**

       ![Der Abschnitt 'Angeheftet Apps'](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Bearbeiten einer App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen (organisationsweiten Standard)-Richtlinie und benutzerdefinierter Richtlinien, die Sie erstellen.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **Teams**  >  **Apps.**

2. Wählen Sie die Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken, und wählen Sie dann **Bearbeiten** aus.

3. Nehmen Sie nun die gewünschten Änderungen vor.

4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit Richtlinien für die App-Einrichtung

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten Richtlinien für die App-Einrichtung sind im Microsoft Teams Admin Center enthalten?

- **Global (Organisationsweite Standardeinstellung):** Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um die Apps anheften, die für Ihre Benutzer am wichtigsten sind.

- **FrontlineWorker:** Diese Richtlinie gilt für Frontline Workers. Sie können sie Mitarbeitern in Frontline in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie von Ihnen erstellte benutzerdefinierte Richtlinien benutzern die Richtlinie zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt Zuweisen einer benutzerdefinierten [App-Setuprichtlinie](#assign-a-custom-app-setup-policy-to-users) zu Benutzern in diesem Artikel.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich im Bereich "Angeheftet Apps hinzufügen" keine App finden?

Nicht alle Apps können über eine App-Teams an die App angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um apps zu finden, die angeheftet werden können, suchen Sie im Bereich **Angeheftet** Apps hinzufügen nach der App. Registerkarten mit einem persönlichen Bereich (statische **Registerkarten)** und Bots können an den Teams-Desktopclient angeheftet werden, und diese Apps sind im Bereich "Angeheftet Apps hinzufügen" verfügbar.

Beachten Sie, dass im Teams App Store alle Teams werden. Der **Bereich Angeheftet Apps hinzufügen** enthält nur Apps, die über eine Richtlinie an Teams angeheftet werden können.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein administrator Teams für Bildungseinrichtungen. Was muss ich über Richtlinien für das App-Setup in Teams Education wissen?

Die Anruf-App ist in Teams Education nicht verfügbar. Wenn Sie eine neue benutzerdefinierte App-Setuprichtlinie erstellen, wird die Aufrufende App in der Liste der Apps angezeigt. Die App ist jedoch nicht an Die Clients Teams angeheftet, und Teams For Education-Benutzer sehen die Anrufe-App nicht in Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Wie viele angeheftet Apps können einer Richtlinie hinzugefügt werden?

Mindestens zwei Apps müssen an die mobilen Teams (iOS und Android) angeheftet werden. Wenn eine Richtlinie weniger als zwei Apps hat, entsprechen die mobilen Clients nicht den Richtlinieneinstellungen und verwenden stattdessen weiterhin die vorhandene Konfiguration.

Die Anzahl der angeheftet Apps, die Sie einer Richtlinie hinzufügen können, ist nicht begrenzt.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden?

Nach Bearbeiten oder Zuweisen einer Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle ihre angeheftet Apps in einem Teams

Um alle Apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen Benutzer je nach Anzahl der installierten Apps und Größe des Teams-Clientfensters möglicherweise die folgenden Schritte tun.

|Teams-Desktopclient |Mobile Microsoft Teams-Clients |
|---------|---------|
|Wählen Sie auf der App-Leiste Teams **aus, ... Weitere Apps**.| Wischen Sie in der App-Leiste Teams Unteren Bildschirmrand nach oben.|
|![Weitere Apps im Teams-Desktopclient](media/app-setup-policies-desktop-more-apps.png)<br>   |![Weitere Apps im mobilen Teams-Client](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die mobile Teams wissen?

Die Teams mobilen Clients (iOS und Android) unterstützen persönliche Apps mit statischen Registerkarten. Apps, die an den Teams-Desktopclients angeheftet sind, werden in den mobilen Teams Clients angezeigt. Persönliche Bots werden in Chat auf mobilen Clients angezeigt.

Apps von Drittanbietern (die über Apps heruntergeladen Teams Store können) müssen genehmigt werden, bevor sie auf mobilen Geräten angezeigt werden. Wenn ein Administrator eine App anheftet, die von Microsoft für Mobile nicht genehmigt wurde, wird sie auf dem Teams-Desktop, aber nicht auf Mobilgeräten angezeigt. Weitere [Informationen finden Sie unter Mobile](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) Clients.

Bei den mobilen Teams-Clients sehen die Benutzer Kern-Teams-Apps wie Aktivität, Chat und Teams, und Sie können einige Erstanbieter-Apps von Microsoft anheften, z. B. Schichten.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge von Apps ändern, die über eine Richtlinie angeheftet sind

Benutzer können die Reihenfolge ihrer angeheftet Apps auf desktop Teams und **mobilen** Clients ändern, wenn die Option Benutzer-Anheften zulassen aktiviert ist. Benutzer können die Reihenfolge ihrer angeheftet Apps auf ihren Webclients Teams ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften von Benutzern Vorrang?

Administratorkontakte haben immer Vorrang. Wenn die **Option Anheften von** Benutzern zulassen aktiviert ist, behalten Benutzer ihre angeheftet Apps unter den angeheftet Admin-Apps. Wenn die **Option Benutzer** anheften zulassen deaktiviert ist, verlieren Benutzer ihre bereits vorhandenen Pins, und nur von Administratoren angeheftet Apps werden in der App-Leiste angezeigt.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-Apps

Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und veröffentlicht, entweder in AppSource oder im Mandanten-App-Katalog, aber das App-Symbol wird nicht wie erwartet angezeigt, wenn die App an die App-Leiste in Teams angeheftet wird. Wie behebt ich das Problem?

Stellen Sie sicher, dass Sie die Logorichtlinien einhalten, bevor Sie die App einreichen. Weitere Informationen finden Sie unter [Prüfliste für die Übermittlung des Verkäufer-Dashboards.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
