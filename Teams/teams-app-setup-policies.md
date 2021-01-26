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
description: Erfahren Sie, wie Sie Richtlinien für die Einrichtung von Apps in Microsoft Teams für Benutzer in Ihrer Organisation verwenden und verwalten.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 32b2accc906b0f4f0dc85b5edf1d9501b64dda14
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909529"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

> [!NOTE]
> Wenn Sie die organisationsweite Einstellung "Interaktion mit benutzerdefinierten Apps zulassen" aktiviert **haben,** werden im Microsoft Teams Admin Center möglicherweise noch keine Richtlinien für die App-Einrichtung angezeigt. Es wird derzeit im Roll out ausgeführt und wird in Kürze in Ihrer Organisation zur Verfügung stehen.

Als Administrator können Sie Richtlinien für die Einrichtung von Apps verwenden, um die folgenden Aufgaben auszuführen:

- Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Sie wählen die Apps aus, die sie anheften möchten, und legen die Reihenfolge fest, in der sie angezeigt werden. Durch das Anheften von Apps können Sie Apps präsentieren, die Benutzer in Ihrer Organisation benötigen, einschließlich Apps, die von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt wurden.
- Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.
- Installieren von Apps im Auftrag von Benutzern **(in der Vorschau).** Sie wählen aus, welche Apps beim Starten von Teams standardmäßig für Benutzer installiert werden. Denken Sie daran, dass Benutzer Apps [](teams-app-permission-policies.md) weiterhin selbst installieren können, wenn die ihnen zugewiesene App-Berechtigungsrichtlinie dies zulässt.

Apps werden an die App-Leiste angeheftet. Dabei handelt es sich um die Leiste an der Seite des Teams-Desktopclients und unten auf den mobilen Teams-Clients (iOS und Android).

|Teams-Desktopclient  |Mobile Microsoft Teams-Clients |
|---------|---------|
|![Der Desktopclient von Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Der mobile Client von Teams](media/mobile-app-ui.png)      |

Um die vorinstallierten Apps zu sehen, wählen Benutzer auf der App-Leiste **... Weitere Apps** in den Desktop- und Webclients von Teams, und wischen Sie in den mobilen Clients nach oben.

Sie verwalten Richtlinien für die Einrichtung von Apps im Microsoft Teams Admin Center. Verwenden Sie die globale (organisationsweite Standardrichtlinie) oder erstellen und weisen Sie benutzerdefinierte Richtlinien zu.  Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie bearbeiten die Einstellungen in der globalen Richtlinie so, dass die von Ihnen verwendeten Apps enthalten sind. Um Teams für verschiedene Benutzergruppen in Ihrer Organisation anzupassen, erstellen und weisen Sie eine oder mehrere benutzerdefinierte Richtlinien zu.

![Die Seite "Richtlinien für die App-Einrichtung"](media/app-setup-policies.png)

> [!NOTE]
> Wenn Sie über Teams für Bildungseinrichtungen verfügen, ist es wichtig zu wissen, dass die App "Aufgaben" standardmäßig in der globalen Richtlinie angeheftet ist, obwohl sie derzeit nicht in der globalen Richtlinie aufgeführt ist. Dies ist die vierte App in der Liste der angeheftet Apps auf Teams-Clients.

## <a name="create-a-custom-app-setup-policy"></a>Erstellen einer benutzerdefinierten App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den Setuprichtlinien **für**  >  **Teams-Apps.**

2. Klicken Sie auf **Hinzufügen**.

   ![Die Seite "App-Setuprichtlinien hinzufügen"](media/app-setup-policies-add.png)
    
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

4. Aktivieren oder deaktivieren Sie **"Benutzerdefinierte Apps hochladen",** je nachdem, ob Benutzer benutzerdefinierte Apps in Teams hochladen können möchten. Sie können diese Einstellung  nicht ändern, wenn "Apps von Drittanbietern zulassen" in [den organisationsweiten App-Einstellungen deaktiviert ist.](manage-apps.md#manage-org-wide-app-settings)

5. Aktivieren oder deaktivieren Sie "Benutzer anheften zulassen", je nachdem, ob Sie benutzern das Personalisieren ihrer App-Leiste durch Anheften von Apps ermöglichen möchten.

   > [!NOTE]
   > Die  Einstellung zum Anheften von Benutzern ist im Teams Admin Center in Microsoft 365 Government Community Cloud (GCC),-Umgebungen (GCC, GCC High und DoD) verfügbar, hat aber zurzeit keine Auswirkung.

6. Zum Installieren von Apps für Benutzer **(in der Vorschau)** gehen Sie wie folgt vor:

    1. Wählen Sie **unter "Installierte Apps"** die Option **"Apps hinzufügen" aus.**
    
    2. Suchen Sie **im Bereich "Installierte Apps** hinzufügen" nach den Apps, die Beim Starten von Teams automatisch installiert werden sollen. Sie können Apps auch nach der Berechtigungsrichtlinie für Apps filtern. Wenn Sie Ihre Liste der Apps ausgewählt haben, wählen Sie **"Hinzufügen" aus.**

       ![Der Bereich "Installierte Apps hinzufügen"](media/app-setup-policies-add-installed-apps.png)

7. Gehen Sie wie folgt vor, um Apps anheften:

    1. Wählen **Sie unter "Angeheftet Apps"** die Option **"Apps hinzufügen" aus.**
    
    2. Suchen Sie **im Bereich "Angeheftet Apps hinzufügen"** nach den Apps, die Sie hinzufügen möchten, und wählen Sie dann "Hinzufügen" **aus.** Sie können Apps auch nach der Berechtigungsrichtlinie für Apps filtern. Wenn Sie Ihre Liste der apps zum Anheften ausgewählt haben, wählen Sie **"Hinzufügen" aus.**

       ![Der Bereich "Angeheftet Apps hinzufügen"](media/app-setup-policies-add-apps.png)

    3. Ordnen Sie die Apps in der Reihenfolge an, in der sie in Teams angezeigt werden sollen, und wählen Sie dann **"Speichern" aus.**

       ![Der Abschnitt "Angeheftet Apps"](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Bearbeiten einer App-Setup-Richtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen Richtlinie (organisationsweite Standardrichtlinie) und der von Ihnen erstellten benutzerdefinierten Richtlinien.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den Setuprichtlinien **für**  >  **Teams-Apps.**

2. Wählen Sie die Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken, und wählen Sie dann **Bearbeiten** aus.

3. Nehmen Sie nun die gewünschten Änderungen vor.

4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit Richtlinien für die Einrichtung von Apps

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten Richtlinien für das Einrichten von Apps sind im Microsoft Teams Admin Center enthalten?

- **Global (organisationsweite Standardeinstellung):** Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um Apps anheften, die für Ihre Benutzer am wichtigsten sind.

- **Frontlineworker:** Diese Richtlinie gilt für Frontline-Mitarbeiter. Sie können sie Den Frontline Workers in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie von Ihnen erstellte benutzerdefinierte Richtlinien den Benutzern die Richtlinie zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt "Zuweisen [einer benutzerdefinierten App-Setuprichtlinie zu Benutzern"](#assign-a-custom-app-setup-policy-to-users) in diesem Artikel.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich eine App im Bereich "Angeheftet Apps hinzufügen" nicht finden?

Nicht alle Apps können über eine App-Setup-Richtlinie an Teams angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um nach Apps zu suchen, die angeheftet werden können, suchen Sie im Bereich "Angeheftet Apps **hinzufügen" nach der** App. Registerkarten mit einem persönlichen Bereich (statische Registerkarten) und Bots können an den Teams-Desktopclient angeheftet werden, und diese Apps stehen im Bereich **"Angeheftet** Apps hinzufügen" zur Verfügung.

Beachten Sie, dass im Store für Teams-Apps alle Teams-Apps aufgeführt sind. Der **Bereich "Angeheftet Apps hinzufügen"** enthält nur Apps, die über eine Richtlinie an Teams angeheftet werden können.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin Ein Administrator für Teams für Bildungseinrichtungen. Was muss ich über Richtlinien für das Einrichten von Apps in Teams für Bildungseinrichtungen wissen?

Die Anruf-App ist in Teams für Bildungseinrichtungen nicht verfügbar. Wenn Sie eine neue benutzerdefinierte App-Setuprichtlinie erstellen, wird die Aufrufende App in der Liste der Apps angezeigt. Die App ist jedoch nicht an Teamclients angeheftet, und Benutzer von Teams für Bildungseinrichtungen sehen die App "Anrufe" in Teams nicht.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Wie viele angeheftet Apps können einer Richtlinie hinzugefügt werden?

Mindestens zwei Apps müssen an die mobilen Clients von Teams (iOS und Android) angeheftet sein. Wenn eine Richtlinie weniger als zwei Apps hat, geben die mobilen Clients die Richtlinieneinstellungen nicht wieder und verwenden stattdessen weiterhin die vorhandene Konfiguration.

Die Anzahl der angeheftet Apps, die Sie einer Richtlinie hinzufügen können, ist nicht begrenzt.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden

Nachdem Sie eine Richtlinie bearbeitet oder zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle ihre angeheftet Apps in Teams sehen?

Um alle Apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen Benutzer je nach Anzahl der installierten Apps und Größe ihres Teams-Clientfensters möglicherweise die folgenden Schritte tun.

|Teams-Desktopclient |Mobile Microsoft Teams-Clients |
|---------|---------|
|Wählen Sie auf der App-Leiste auf der Seite von Teams **... "Weitere Apps" aus.**| Wischen Sie in der App-Leiste am unteren Rand von Teams nach oben.|
|![Weitere Apps im Desktopclient von Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Weitere Apps im mobilen Client von Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die mobile Erfahrung in Teams wissen?

Die mobilen Teams-Clients (iOS und Android) unterstützen zurzeit keine persönlichen Apps mit statischen Registerkarten. Je nach den in der Richtlinie festgelegten Apps werden an den Desktopclient von Teams angeheftete Apps möglicherweise nicht in den mobilen Teams-Clients angezeigt. Persönliche Bots werden weiterhin in Chat auf mobilen Clients angezeigt.

Bei den mobilen Microsoft Teams-Clients sehen die Benutzer die wichtigsten Teams-Apps, z. B. "Aktivität", "Chat" und "Teams", und Sie können einige Apps von Microsoft von Microsoft anheften, z. B. Schichten.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge von Apps ändern, die über eine Richtlinie angeheftet sind

Benutzer können die Reihenfolge ihrer angeheftet Apps auf teams-Desktop- und **mobilen** Clients ändern, wenn die Option zum Anheften von Benutzern aktiviert ist. Benutzer können die Reihenfolge ihrer angeheftet Apps auf Teams-Webclients nicht ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften von Benutzern Vorrang?

Wenn die dem Benutzer zugewiesene App-Setup-Richtlinie so geändert wird, dass das Anheften von Benutzer-Apps blockiert wird, entfernt Teams alle Apps, die an die App-Leiste angeheftet sind. Wenn die Richtlinie geändert wird, um das Anheften von Benutzer-Apps zu ermöglichen, müssen die Benutzer ihre zuvor angeheftet Apps erneut anheften.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-Apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und veröffentlicht, entweder in AppSource oder im Mandanten-App-Katalog, aber das App-Symbol wird nicht wie erwartet angezeigt, wenn die App in Teams an die App-Leiste angeheftet ist. Wie behebt ich das Problem?

Stellen Sie sicher, dass Sie die Logorichtlinien einhalten, bevor Sie die App übermitteln. Weitere Informationen finden Sie unter [Prüfliste für die Übermittlung von Verkäuferdashboards.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)
