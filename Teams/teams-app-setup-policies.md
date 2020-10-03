---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Hier erfahren Sie, wie Sie App-Setup Richtlinien in Microsoft Teams für Benutzer in Ihrer Organisation verwenden und verwalten.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: d3928bd15ab5b023c025024f2dbf05c404adeee6
ms.sourcegitcommit: fae47764336b47c65e9e24b9abd6fe23ad9fc1a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341103"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

> [!NOTE]
> Wenn Sie die organisationsweite app-Einstellung aktiviert haben, die **Interaktion mit benutzerdefinierten apps zulassen**, werden die APP-Setup Richtlinien möglicherweise noch nicht im Microsoft Teams Admin Center angezeigt. Sie wird zurzeit bereitgestellt und wird in Kürze in Ihrer Organisation zur Verfügung stehen.

Als Administrator können Sie die APP-Setup Richtlinien verwenden, um die folgenden Aufgaben auszuführen:

- Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Sie wählen die Apps aus, die Sie anheften möchten, und legen die Reihenfolge fest, in der Sie angezeigt werden. Mit Anheften von Apps können Sie apps präsentieren, die von Benutzern in Ihrer Organisation benötigt werden, einschließlich von apps, die von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt wurden.
- Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.
- Installieren von apps im Auftrag von Benutzern **(in der Vorschau)** Sie wählen die Apps aus, die standardmäßig für Benutzer installiert werden, wenn Sie Teams starten. Beachten Sie, dass Benutzer weiterhin Apps selbst installieren können, wenn die Ihnen zugewiesene [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) dies zulässt.

Apps werden an die APP-Leiste angeheftet, die die Leiste auf der Seite des Teams-Desktop Clients und am unteren Rand des Teams Mobile Clients (IOS und Android) ist.

|Desktop Client für Teams  |Mobiler Client für Teams |
|---------|---------|
|![Der Desktop Client von Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Der Mobile Client für Teams](media/mobile-app-ui.png)      |

Um die vorinstallierten apps anzuzeigen, wählen Sie in der APP-Leiste Benutzer aus **... Weitere apps** in den Teams-Desktop-und-Webclients und wischen Sie in den mobilen Clients nach oben.

Sie verwalten App-Setup Richtlinien im Microsoft Teams Admin Center. Verwenden Sie die globale (organisationsweite Standardrichtlinie), oder erstellen Sie benutzerdefinierte Richtlinien, und weisen Sie diese zu.  Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie bearbeiten die Einstellungen in der globalen Richtlinie, um die gewünschten apps einzubeziehen. Um Teams für verschiedene Benutzergruppen in Ihrer Organisation anzupassen, erstellen Sie eine oder mehrere benutzerdefinierte Richtlinien, und weisen Sie diese zu.

![Seite "Richtlinien für die APP-Installation"](media/app-setup-policies.png)

> [!NOTE]
> Wenn Sie über Teams für Bildung verfügen, ist es wichtig zu wissen, dass die Aufgaben-App standardmäßig in der globalen Richtlinie angeheftet ist, obwohl Sie in der globalen Richtlinie zurzeit nicht aufgeführt ist. Es handelt sich um die vierte app in der Liste der angehefteten apps auf Teams-Clients.

## <a name="create-a-custom-app-setup-policy"></a>Erstellen einer benutzerdefinierten App-Setup Richtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**den  >  **Setup Richtlinien**für Teams-apps.
2. Wählen Sie **Hinzufügen**aus.
    ![Seite "Richtlinien zum Hinzufügen von Apps"](media/app-setup-policies-add.png)
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Aktivieren oder deaktivieren Sie Benutzer **definierte apps hochladen**, je nachdem, ob Sie Benutzer benutzerdefinierte apps in Teams hochladen lassen möchten. Sie können diese Einstellung nicht ändern, wenn das **Zulassen von Drittanbieter-apps** in den [organisationsweiten App-Einstellungen](manage-apps.md#manage-org-wide-app-settings)deaktiviert ist.
5. Aktivieren oder deaktivieren Sie das **Zulassen von Benutzer anheften**, je nachdem, ob Benutzer Ihre APP-Leiste personalisieren lassen möchten, indem Sie apps an Sie anheften.
6. Führen Sie die folgenden Aufgaben aus, um Apps für Benutzer **(in der Vorschau)** zu installieren:

    1. Wählen Sie unter **installierte apps**die Option **apps hinzufügen**aus.
    2. Suchen Sie im Bereich **installierte apps hinzufügen** nach den apps, die Sie beim Starten von Teams automatisch für Benutzer installieren möchten. Sie können apps auch nach App-Berechtigungsrichtlinien filtern. Wenn Sie die Liste der apps ausgewählt haben, wählen Sie **Hinzufügen**aus.

        ![der Bereich "installierte apps hinzufügen"](media/app-setup-policies-add-installed-apps.png)

7. Gehen Sie wie folgt vor, um apps zu anheften:

    1. Wählen Sie unter **angeheftete apps**die Option **apps hinzufügen**aus.
    2. Suchen Sie im Bereich **angeheftete apps hinzu** fügen nach den apps, die Sie hinzufügen möchten, und wählen Sie dann **Hinzufügen**aus. Sie können apps auch nach App-Berechtigungsrichtlinien filtern. Wenn Sie die Liste der zu anheftenden apps ausgewählt haben, wählen Sie **Hinzufügen**aus.

         ![der Bereich "angeheftete apps hinzufügen"](media/app-setup-policies-add-apps.png)

    3. Ordnen Sie die apps in der Reihenfolge an, in der Sie in Teams angezeigt werden sollen, und wählen Sie dann **Speichern**aus.

        ![der Abschnitt angeheftete apps](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Bearbeiten einer APP-Setup Richtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der Global (org-Wide Standard)-Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**den  >  **Setup Richtlinien**für Teams-apps.
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken, und wählen Sie dann **Bearbeiten**aus.
3. Nehmen Sie hier die gewünschten Änderungen vor.
4. Wählen Sie **Speichern**aus.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Setup Richtlinie für Benutzer

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit App-Setup Richtlinien

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten App-Setup Richtlinien sind im Microsoft Teams Admin Center enthalten

- **Global (org-Wide Standard)**: Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um apps zu anheften, die für Ihre Benutzer am wichtigsten sind.
- **FirstLineWorker**: Diese Richtlinie gilt für First-work-Mitarbeiter. Sie können es den Mitarbeitern in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie von Ihnen erstellte benutzerdefinierte Richtlinien die Richtlinie Benutzern zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt [Zuweisen einer benutzerdefinierten App-Setup Richtlinie zu Benutzern](#assign-a-custom-app-setup-policy-to-users) dieses Artikels.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich keine app im Bereich "angeheftete apps hinzufügen" finden?

Nicht alle apps können über eine APP-Setup Richtlinie an Teams angeheftet werden. Einige apps unterstützen diese Funktion möglicherweise nicht. Um apps zu finden, die angeheftet werden können, suchen Sie im Bereich **angeheftete apps hinzufügen** nach der app. Registerkarten mit einem persönlichen Bereich (statische Registerkarten) und Bots können an den Desktop Client von Teams angeheftet werden, und diese apps sind im Bereich **angeheftete apps hinzufügen** verfügbar.

Beachten Sie, dass im App Store für Teams alle Teams-apps aufgelistet sind. Der Bereich **angeheftete apps hinzufügen** enthält nur apps, die über eine Richtlinie an Teams angeheftet werden können.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein Team für Bildungs Administrator. Was muss ich über die Richtlinien für die APP-Einrichtung in Teams für Bildung wissen?

Die Anruf-App steht in Teams für Education nicht zur Verfügung. Wenn Sie eine neue benutzerdefinierte App-Setup Richtlinie erstellen, wird die aufrufende app in der Liste der apps angezeigt. Die APP wird jedoch nicht an Teams-Clients und Teams für Education angeheftet. Benutzer sehen die Anruf-APP nicht in Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Wie viele angeheftete apps einer Richtlinie hinzugefügt werden können

Mindestens zwei apps müssen an die mobilen Teams (IOS und Android) angeheftet sein. Wenn eine Richtlinie weniger als zwei apps aufweist, geben die mobilen Clients die Richtlinieneinstellungen nicht wieder und verwenden stattdessen weiterhin die vorhandene Konfiguration.

Die Anzahl der angehefteten apps, die Sie einer Richtlinie hinzufügen können, ist unbegrenzt.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden?

Nachdem Sie eine Richtlinie bearbeitet oder zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle Ihre angehefteten apps in Microsoft Teams anzeigen?

Um alle apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen die Benutzer möglicherweise die folgenden Schritte ausführen, abhängig von der Anzahl der installierten apps und der Größe des Teams-Clientfensters.

|Desktop Client für Teams |Mobiler Client für Teams |
|---------|---------|
|Wählen Sie in der APP-Leiste auf der Seite von Teams die Option **... Weitere apps**.| Wischen Sie in der APP-Leiste am unteren Rand von Teams nach oben.|
|![Weitere apps im Desktop Client von Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Weitere apps im mobilen Microsoft Teams-Client](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die Mobile Teams-Umgebung wissen?

Die Mobile-Clients von Teams (IOS und Android) unterstützen derzeit keine persönlichen apps mit statischen Registerkarten. Je nach den in der Richtlinie festgelegten apps werden apps, die an den Desktop Client von Teams angeheftet wurden, möglicherweise nicht in den mobilen Teams angezeigt. Persönliche Bots werden weiterhin im Chat auf mobilen Clients angezeigt.

Mit den mobilen Teams von Teams werden Benutzern Kern Teams-apps wie Aktivitäten, Chats und Teams angezeigt, und Sie können einige Erstanbieter-apps von Microsoft anheften, beispielsweise Schichten.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge der apps ändern, die über eine Richtlinie angeheftet sind

Benutzer können die Reihenfolge ihrer angehefteten apps auf den Desktop-und mobilen Clients von Teams ändern, wenn die Option **Benutzer anheften zulassen** aktiviert ist. Benutzer können die Reihenfolge ihrer angehefteten apps auf den Microsoft Teams-Webclients nicht ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften von Benutzern Vorrang

Wenn die dem Benutzer zugewiesene App-Setup Richtlinie geändert wird, um das Anheften der Benutzer-APP zu blockieren, entfernt Teams alle apps, die an die APP-Leiste angeheftet sind. Wenn die Richtlinie dann geändert wird, um Benutzer-App-anheften zuzulassen, müssen Benutzer ihre zuvor angehefteten apps erneut anheften.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und Sie entweder in AppSource oder im Mandanten-App-Katalog veröffentlicht, doch das App-Symbol wird nicht wie erwartet angezeigt, wenn die app in Teams an die APP-Leiste angeheftet wird. Wie behebe ich es

Achten Sie darauf, dass Sie die Richtlinien für das Logo befolgen, bevor Sie die APP übermitteln. Weitere Informationen finden Sie unter [Checkliste für die Übermittlung von Verkäufer Dashboards](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
