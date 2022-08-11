---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
description: Erfahren Sie, wie Sie App-Setuprichtlinien erstellen, bearbeiten und verwalten, um Apps anzuheften, Apps zu installieren und Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 2788c1caeef3c6fcc1c0464c8e9289bcbd65508f
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "67298874"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

Als Administrator verwenden Sie App-Setuprichtlinien, um Apps zu installieren und anzuheften und Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen. Das Anheften trägt dazu bei, die Einführung relevanter Apps in Ihrer Organisation zu fördern.

* **Apps anheften:** Mit App-Setuprichtlinien können Sie Apps auswählen, die angeheftet werden sollen, und die Reihenfolge festlegen, in der die Apps für Ihre Benutzer in der Microsoft Teams-App-Leiste oder im Bereich zum Verfassen von Nachrichten angezeigt werden. Administratoren können auch steuern, ob die Endbenutzer ihre eigenen Apps anheften können oder nicht. Siehe [Anheften von Apps](#pin-apps).
* **Apps installieren:** Mithilfe von App-Setuprichtlinien können Sie die zulässigen Apps im Namen von Benutzern beim Start von Microsoft Teams und während Besprechungen installieren. Weitere Informationen finden Sie unter [Installieren von Apps](#install-apps).
* **Benutzerdefinierte Apps hochladen:** Mithilfe von App-Setuprichtlinien können Sie Benutzern erlauben, benutzerdefinierte Apps in Microsoft Teams hochzuladen. Weitere Informationen finden Sie unter [Hochladen benutzerdefinierter Apps](teams-custom-app-policies-and-settings.md).

Die folgenden integrierten App-Setuprichtlinien sind standardmäßig im Microsoft Teams Admin Center verfügbar:

* **Global (organisationsweiter Standard):** Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um Apps anzuheften, die für Ihre Benutzer am wichtigsten sind.

* **FirstlineWorker**: Diese Richtlinie gilt für Mitarbeiter in Service und Produktion. Die Richtlinie kann nicht angepasst werden. Sie können sie Mitarbeitern in Service und Produktion in Ihrer Organisation zuweisen.

## <a name="pin-apps"></a>Apps anheften

Durch das Anheften von Apps können Sie Apps hervorheben, die Benutzer in Ihrer Organisation am meisten benötigen. Das Anheften funktioniert für Apps aller Art in Microsoft Teams – Core-Apps, von Microsoft bereitgestellte Apps, Drittanbieter-Apps und benutzerdefinierte Apps, die in Ihrer Organisation entwickelt wurden. Wenn Sie eine App über eine App-Setuprichtlinie anheften, wird sie auch installiert, sofern die App für den Benutzer zulässig ist. Mithilfe einer App-Setuprichtlinie können Sie die folgenden Aufgaben ausführen:

* Passen Sie Microsoft Teams für Endbenutzer, um die wichtigsten Apps für sie hervorzuheben. Wählen Sie die Apps aus, die Sie anheften möchten, und legen Sie die Reihenfolge fest, in der sie angezeigt werden sollen.
* Legen Sie fest, ob Benutzer Apps Teams anheften können oder nicht.

Apps werden an die App-Leiste auf der linken Seite des Microsoft Teams-Desktopclients bzw. am unteren Rand in mobilen Microsoft Teams-Clients angeheftet.

|Microsoft Teams-Desktopclient  |Mobile Microsoft Teams-Clients |
|---------|---------|
|![App-Leiste im Microsoft Teams-Desktopclient.](media/app-setup-policies-desktop-app-bar.png).  |   ![App-Leiste im mobilen Microsoft Teams-Client.](media/mobile-app-ui.png)      |

Die Messaging-Erweiterungen sind unten im Bereich zum Verfassen von Nachrichten verfügbar.

Führen Sie die folgenden Schritte aus, um Apps mithilfe einer App-Setuprichtlinie anzuheften:

1. Melden Sie sich beim Microsoft Teams Admin Center an, und greifen Sie auf **Microsoft Teams-Apps** > **[Setuprichtlinien](https://admin.teams.microsoft.com/policies/app-setup)** zu.

1. Klicken Sie auf **Hinzufügen**.

1. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

1. Aktivieren Sie die **Anheften durch Benutzer**.

   > [!NOTE]
   > Die Einstellung **Anheften durch Benutzer** ist im Microsoft Teams Admin Center in Microsoft 365 Government Community Cloud (GCC)-Umgebungen (GCC, GCC High und DoD) verfügbar, hat aber keine Auswirkung.

1. Wählen Sie unter **Angeheftete Apps** die Option **Apps hinzufügen** aus.

1. Suchen Sie im Bereich **angeheftete Apps hinzufügen** nach den Apps, die Sie hinzufügen möchten, und wählen Sie dann **Hinzufügen** aus. Sie können Apps auch nach App-Berechtigungsrichtlinien filtern.

1. Klicken Sie auf **Hinzufügen**.

1. Ordnen Sie die Apps auf der **App-Leiste** oder unter **Messaging-Erweiterungen** in der Reihenfolge an, in der sie in Microsoft Teams angezeigt werden sollen.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Screenshot: Angeheftete Apps und angeheftete Messaging-Erweiterungen in der Setuprichtlinie.":::

1. Klicken Sie auf **Speichern**.

> [!NOTE]
> Für die Mitarbeiter in Service und Produktion in Ihrer Organisation empfehlen wir die Verwendung der maßgeschneiderten App-Umgebung für Service und Produktion. Dieses Feature heftet die relevantesten Apps in Microsoft Teams für Benutzer an, die über eine [F-Lizenz](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt) verfügen. Weitere Informationen finden Sie unter Passen Sie [Teams-Apps für Ihre Außendienstmitarbeiter an](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Installieren von Apps

Mithilfe einer App-Setuprichtlinie können Administratoren die folgenden Aufgaben ausführen:

* Installieren von Apps für Endbenutzer in deren persönlicher Microsoft Teams-Umgebung.
* Installieren von Apps für Endbenutzer als [Messaging-Erweiterungen](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Die Endbenutzer können Apps selbst installieren, wenn die [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) dies zulässt und die App selbst auf ihrem Mandanten zulässig ist.

Führen Sie die folgenden Schritte aus, um eine App-Setuprichtlinie zum Installieren von Apps zu erstellen:

1. Melden Sie sich beim Microsoft Teams Admin Center an, und greifen Sie auf **Microsoft Teams-Apps** > **[Setuprichtlinien](https://admin.teams.microsoft.com/policies/app-setup)** zu.

1. Klicken Sie auf **Hinzufügen**.

1. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

1. Wählen Sie im Abschnitt **Installierte Apps** die Option **Apps hinzufügen** aus.

1. Suchen Sie im Bereich **Installierte Apps hinzufügen** die Apps, die Sie für Benutzer installieren möchten. Sie können Apps auch nach App-Berechtigungsrichtlinien filtern.

1. Klicken Sie auf **Hinzufügen**.

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="Installieren Sie die App-Richtlinie.":::

## <a name="manage-app-setup-policies"></a>Verwalten von Richtlinien für App-Setup in Teams

Richtlinien für das App-Setup verwalten Sie im Microsoft Teams Admin Center. Verwenden Sie die globale (organisationsweite Standard-) Richtlinie, oder erstellen Sie benutzerdefinierte Richtlinien, und weisen Sie diese zu. Endbenutzer erhalten die globale Richtlinie. Wenn Sie eine benutzerdefinierte Richtlinie erstellen, überschreibt diese die globale Richtlinie. Globale Administratoren oder Microsoft Teams-Dienstadministratoren können diese Richtlinien verwalten.

Sie bearbeiten die Einstellungen in der globalen Richtlinie, um die gewünschten Apps einzuschließen. Wenn Sie Microsoft Teams für unterschiedliche Benutzergruppen in Ihrer Organisation anpassen möchten, können Sie eine oder mehrere benutzerdefinierte Richtlinien erstellen und zuweisen.

![Seite „App-Setuprichtlinien“ zum verwalten von Richtlinien oder Hinzufügen neuer Richtlinien.](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>Bearbeiten einer App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen (organisationsweiten Standardrichtlinie) und benutzerdefinierten Richtlinien, die Sie erstellen.

1. Melden Sie sich beim Microsoft Teams Admin Center an, und greifen Sie auf **Microsoft Teams-Apps** > **[Setuprichtlinien](https://admin.teams.microsoft.com/policies/app-setup)** zu.

1. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** aus.

1. Nehmen Sie die gewünschten Änderungen vor.

1. Klicken Sie auf **Speichern**.

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern und Gruppen

Wenn Sie wissen möchten, wie Sie Ihren Endbenutzern und Gruppen Richtlinien zuweisen, lesen Sie [Zuweisen von Richtlinien zu Benutzern und Gruppen](assign-policies-users-and-groups.md).

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

* Sie können mit App-Setuprichtlinien keine benutzerdefinierten Apps mit konfigurierbaren Registerkarten installieren.
* Endbenutzer können eine App, die von einem Administrator installiert wurde, nicht deinstallieren.
* Über die App-Setuprichtlinie angeheftete Apps können vom Benutzer gelöst werden (wenn das Anheften durch Benutzer in der Setuprichtlinie zulässig ist).
* In Microsoft Teams für Education ist die Aufgaben-App standardmäßig in der globalen Richtlinie angeheftet, obwohl sie nicht in der globalen Richtlinie aufgeführt ist.
* Die Anzahl der angehefteten Anwendungen, die Sie einer Richtlinie hinzufügen können, ist nicht begrenzt. Es müssen jedoch mindestens zwei Apps an die mobilen Microsoft Teams-Clients (iOS und Android) angeheftet werden. Wenn eine Richtlinie weniger als zwei Apps umfasst, werden die Einstellungen der Richtlinie nicht auf die mobilen Clients übertragen, sondern die bestehende Konfiguration wird weiter verwendet.
* Nach Bearbeiten oder Zuweisen einer Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden.

## <a name="faqs"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Verwenden von App-Setuprichtlinien

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum wird eine App nicht im Bereich „Angeheftete Anwendungen hinzufügen“ angezeigt?

Nicht alle Apps können über eine App-Setuprichtlinie an Teams angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um Apps zu finden, die angeheftet werden können, suchen Sie diese im Bereich **Angeheftete Apps hinzufügen**. Registerkarten mit einem persönlichen Bereich (statische Registerkarten) und Bots können an den Teams-Desktopclient angeheftet werden, und diese Apps sind im Bereich **Angeheftete Apps hinzufügen** verfügbar.

Beachten Sie, dass im Teams-App Store alle Teams-Apps aufgelistet sind. Der Bereich **Angeheftete Apps hinzufügen** enthält nur Apps, die über eine Richtlinie an Teams angeheftet werden können.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein Microsoft Teams für Education-Administrator. Was muss ich über App-Setuprichtlinien in Microsoft Teams für Education wissen?

Die App für Anrufe ist in Microsoft Teams für Education nicht verfügbar. Wenn Sie eine neue benutzerdefinierte App-Setuprichtlinie erstellen, wird die Anruf-App in der Liste der Apps angezeigt. Die App wird jedoch nicht an Microsoft Teams-Clients angeheftet, und Benutzern von Microsoft Teams für Education wird die Anruf-App in Teams nicht angezeigt.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle angehefteten Apps in Teams anzeigen?

Um alle Apps anzuzeigen, die für einen Benutzer angeheftet wurden, müssen Benutzer abhängig von der Anzahl der installierten Apps und der Größe ihres Microsoft Teams-Clientfensters möglicherweise folgende Schritte ausführen.

|Microsoft Teams-Desktopclient |Mobile Microsoft Teams-Clients |
|---------|---------|
|Wählen Sie in der App-Leiste auf der Seite von Teams **...Weitere Apps** aus.| Wischen Sie in der App-Leiste am unteren Rand von Teams nach oben.|
|![Weitere Apps im Teams-Desktopclient.](media/app-setup-policies-desktop-more-apps.png)   |![weitere Apps im mobilen Microsoft Teams-Client](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die mobile Microsoft Teams-Umgebung wissen?

Die mobilen Microsoft Teams-Clients (iOS und Android) unterstützen persönliche Apps mit statischen Registerkarten. An den Microsoft Teams-Desktopclient angeheftete Apps werden in den mobilen Microsoft Teams-Clients angezeigt. Persönliche Bots werden im Chat auf mobilen Clients angezeigt.

Drittanbieter-Apps (die aus dem Teams Store heruntergeladen werden können) müssen genehmigt werden, bevor sie auf Mobilgeräten angezeigt werden. Wenn ein Administrator eine App anheftet, die von Microsoft für Mobile nicht genehmigt wurde, wird sie auf dem Microsoft Teams-Desktop angezeigt, aber nicht auf mobilen Geräten. Weitere Informationen finden Sie unter [Mobile Clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients).

Mit den mobilen Clients von Teams sehen die Benutzer die wichtigsten Teams-Apps wie Aktivität, Chat und Teams, und Sie können von Microsoft bereitgestellte Apps anheften.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge von über eine Richtlinie angehefteten Apps ändern?

Benutzer können die Reihenfolge ihrer angehefteten Apps auf Microsoft Teams-Desktop- und mobilen Clients ändern, wenn die Option **Anheften durch Benutzer** aktiviert ist. Benutzer können die Reihenfolge ihrer angehefteten Apps auf Microsoft Teams-Webclients nicht ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften durch Benutzer Vorrang

Von Administratoren angeheftete Apps haben immer Vorrang. Wenn die Option **Anheften durch Benutzer** aktiviert ist, bleiben die vom Benutzer angehefteten Apps unter den vom Administrator angehefteten Apps erhalten. Wenn die Option **Anheften durch Benutzer** deaktiviert ist, gehen die bereits vorhandenen angehefteten Apps der Benutzer verloren, und in der App-Leiste werden nur noch die von Administratoren angehefteten Apps angezeigt.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Microsoft Teams-Apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und veröffentlicht, entweder in AppSource oder im Mandanten-App-Katalog, aber das App-Symbol wird nicht wie erwartet angezeigt, wenn die App an die App-Leiste in Microsoft Teams angeheftet wird. Problemlösung

Stellen Sie sicher, dass Sie die Logorichtlinien befolgen, bevor Sie die App übermitteln. Weitere Informationen finden Sie unter [Checkliste für die Übermittlung an das Verkäuferdashboard](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-articles"></a>Verwandte Artikel

* [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
* [Zuweisen von Richtlinien zu Endbenutzern in Microsoft Teams](assign-policies-users-and-groups.md)
