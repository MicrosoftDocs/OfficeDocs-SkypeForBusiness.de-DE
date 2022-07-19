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
description: Erfahren Sie, wie Sie App-Setuprichtlinien erstellen, bearbeiten und verwalten, um Apps anzuheften, Apps zu installieren und Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: b97f6c490f562cbd860e6c69a09e3659340dea99
ms.sourcegitcommit: 791d0a341ff873145fa893ece05055729b0b8d50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2022
ms.locfileid: "66838800"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

Als Administrator verwenden Sie App-Setuprichtlinien, um Apps zu installieren und anzuheften und Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen. Das Anheften trägt dazu bei, die Einführung relevanter Apps in Ihrer Organisation zu fördern.

* **Apps anheften:** Mit App-Setuprichtlinien können Sie Apps auswählen, die angeheftet werden sollen, und die Reihenfolge festlegen, in der die Apps für Ihre Benutzer in der Teams-App-Leiste oder im Nachrichtenbereich zum Verfassen angezeigt werden. Administratoren können auch steuern, ob die Endbenutzer ihre eigenen Apps anheften können oder nicht. Siehe [Pin-Apps](#pin-apps).
* **Installieren von Apps:** Mithilfe von App-Setuprichtlinien können Sie die zulässigen Apps im Namen von Benutzern installieren, wenn sie Teams starten und während Besprechungen. Weitere Informationen finden [Sie unter "Installieren von Apps"](#install-apps).
* **Benutzerdefinierte Apps hochladen:** App-Setuprichtlinien ermöglichen Es Benutzern, benutzerdefinierte Apps in Teams hochzuladen. Weitere Informationen finden [Sie unter Hochladen benutzerdefinierter Apps](#upload-custom-apps).

## <a name="pin-apps"></a>Apps anheften

Durch das Anheften von Apps können Sie Apps hervorheben, die Benutzer in Ihrer Organisation am meisten benötigen. Das Anheften funktioniert für Apps, die von Microsoft, von ISV-Firmen und von Entwicklern in Ihrer Organisation bereitgestellt werden. Wenn Sie eine App über eine App-Setuprichtlinie anheften, wird sie auch installiert, wenn die App für den Benutzer zulässig ist. Mithilfe einer App-Setuprichtlinie können Sie die folgenden Aufgaben ausführen:

* Passen Sie Microsoft Teams für Endbenutzer an, um die wichtigsten Apps für sie hervorzuheben. Sie wählen die anzuheftenden Apps und die Reihenfolge aus, in der die Apps angezeigt werden.
* Steuern, ob Benutzer Apps anheften können oder nicht.

Apps werden an die App-Leiste auf der linken Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients angeheftet.

|Microsoft Teams-Desktopclient  |Mobile Microsoft Teams-Clients |
|---------|---------|
|![App-Leiste im Teams-Desktopclient.](media/app-setup-policies-desktop-app-bar.png).  |   ![App-Leiste im mobilen Microsoft Teams-Client.](media/mobile-app-ui.png)      |

Die Messaging-Erweiterungen sind unten im Nachrichtenbereich zum Verfassen verfügbar.

Führen Sie die folgenden Schritte aus, um eine App-Setuprichtlinie zum Anheften von Apps zu erstellen:

1. Melden Sie sich beim [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) an.

1. Wechseln Sie im linken Bereich zu **Setuprichtlinien** für **Teams-Apps** > .

1. Klicken Sie auf **Hinzufügen**.

1. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

1. Aktivieren Sie **die Benutzer-Anheftung**.

   > [!NOTE]
   > Die Einstellung zum **Anheften von Benutzern** ist im Teams Admin Center in Microsoft 365 Government Community Cloud (GCC)-Umgebungen (GCC, GCC High und DoD) verfügbar, hat aber derzeit keine Auswirkungen.

1. Wählen Sie unter **"Angeheftete Apps**" die Option **"Apps hinzufügen"** aus.

1. Suchen Sie im Bereich **"Angeheftete Apps hinzufügen** " nach den Apps, die Sie hinzufügen möchten, und wählen Sie dann **"Hinzufügen"** aus. Sie können Apps auch nach App-Berechtigungsrichtlinie filtern.

1. Klicken Sie auf **Hinzufügen**.

1. Ordnen Sie die Apps unter der **App-Leiste** oder **messaging-Erweiterungen** in der Reihenfolge an, in der sie in Teams angezeigt werden sollen.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Abschnitt &quot;Angeheftete Apps&quot;"border="true":::

1. Klicken Sie auf **Speichern**.

> [!NOTE]
> In Teams für Education ist die Zuweisungs-App standardmäßig in der globalen Richtlinie angeheftet, obwohl sie in der globalen Richtlinie nicht aufgeführt ist.

> [!NOTE]
> Für die Mitarbeiter in Service und Produktion in Ihrer Organisation empfehlen wir die Verwendung der maßgeschneiderten App-Erfahrung in Service und Produktion. Dieses Feature heftt die relevantesten Apps in Teams für Benutzer an, die über eine [F-Lizenz](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt) verfügen. Weitere Informationen finden Sie [unter "Anpassen von Teams-Apps für Ihre Mitarbeiter in Service und Produktion](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)".

## <a name="install-apps"></a>Installieren von Apps

Mithilfe einer App-Setuprichtlinie kann ein Administrator die folgenden Aufgaben ausführen:

* Installieren Sie Apps für Endbenutzer standardmäßig in ihrer persönlichen Teams-Umgebung.
* Installieren Sie Apps für Endbenutzer als [Messaging-Erweiterungen](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Die Endbenutzer können Apps selbst installieren, wenn die [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) dies zulässt.

Führen Sie die folgenden Schritte aus, um eine App-Setuprichtlinie zum Installieren von Apps zu erstellen:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Setuprichtlinien** für **Teams-Apps** >  zu.

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie an.

4. Wählen Sie unter **"Installierte Apps**" die Option **"Apps hinzufügen"** aus.

5. Suchen Sie im Bereich **"Installierte Apps hinzufügen** " die Apps, die Sie für Benutzer installieren möchten. Sie können Apps auch nach App-Berechtigungsrichtlinie filtern.

6. Klicken Sie auf **Hinzufügen**.

![Installieren Sie die App-Richtlinie.](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> Benutzer können keine Apps deinstallieren, die von Administratoren installiert wurden.

>[!NOTE]
> Mit diesem Verfahren können Sie keine benutzerdefinierten Apps mit konfigurierbaren Registerkarten installieren.

## <a name="upload-custom-apps"></a>Hochladen benutzerdefinierter Apps

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Richtlinie zu erstellen, mit der Benutzer benutzerdefinierte Apps hochladen können:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Setuprichtlinien** für **Teams-Apps** >  zu.

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie an.

4. Aktivieren oder deaktivieren **Sie "Benutzerdefinierte Apps hochladen**".

> [!NOTE]
> Um diese Einstellung zu ändern, müssen die [organisationsweiten App-Einstellungen](manage-apps.md#manage-org-wide-app-settings) Ihres Mandanten **Apps von Drittanbietern** zulassen.

## <a name="manage-app-setup-policies"></a>Verwalten von App-Setuprichtlinien

Sie verwalten App-Setuprichtlinien im Microsoft Teams Admin Center. Verwenden Sie die globale Richtlinie (organisationsweite Standardrichtlinie), oder erstellen und weisen Sie benutzerdefinierte Richtlinien zu. Endbenutzer erhalten die globale Richtlinie. Wenn Sie eine benutzerdefinierte Richtlinie erstellen, überschreibt sie die globale Richtlinie. Dieser globale Administrator oder Teams-Dienstadministrator kann diese Richtlinien verwalten.

Sie bearbeiten die Einstellungen in der globalen Richtlinie, um die gewünschten Apps einzuschließen. Um Teams für verschiedene Benutzergruppen in Ihrer Organisation anzupassen, erstellen und weisen Sie eine oder mehrere benutzerdefinierte Richtlinien zu.

![Seite "App-Setuprichtlinien", um Richtlinien zu verwalten oder neue Richtlinien hinzuzufügen.](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>Bearbeiten einer App-Setuprichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen (organisationsweiten Standardrichtlinie) und benutzerdefinierten Richtlinien, die Sie erstellen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Einrichtungsrichtlinien**.

2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **"Bearbeiten"** aus.

3. Nehmen Sie die gewünschten Änderungen vor.

4. Klicken Sie auf **Speichern**.

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern und Gruppen

Weitere Informationen zum Zuweisen von Richtlinien zu Ihren Benutzern und Gruppen finden Sie unter [Zuweisen von Richtlinien zu Benutzern und Gruppen](assign-policies-users-and-groups.md).

## <a name="faqs"></a>Faqs

<!--- TBD: Incorporate these pointers in the content itself.
--->

### <a name="working-with-app-setup-policies"></a>Arbeiten mit App-Setuprichtlinien

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten App-Setuprichtlinien sind im Microsoft Teams Admin Center enthalten?

* **Global (organisationsweiter Standard):** Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um Apps anzuheften, die für Ihre Benutzer am wichtigsten sind.

* **FrontlineWorker**: Diese Richtlinie richtet sich an Mitarbeiter in Service und Produktion. Sie können es Mitarbeitern in Service und Produktion in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie benutzerdefinierte Richtlinien, die Sie erstellen, benutzern die Richtlinie zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt " [Zuweisen einer benutzerdefinierten App-Setuprichtlinie zu Benutzern](#assign-a-custom-app-setup-policy-to-users-and-groups) " in diesem Artikel.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich im Bereich "Angeheftete Apps hinzufügen" keine App finden?

Nicht alle Apps können über eine App-Setuprichtlinie an Teams angeheftet werden. Einige Apps unterstützen diese Funktionalität möglicherweise nicht. Um Apps zu finden, die angeheftet werden können, suchen Sie im Bereich " **Angeheftete Apps hinzufügen** " nach der App. Registerkarten mit einem persönlichen Bereich (statische Registerkarten) und Bots können an den Teams-Desktopclient angeheftet werden, und diese Apps sind im Bereich **"Angeheftete Apps hinzufügen"** verfügbar.

Beachten Sie, dass im Teams-App Store alle Teams-Apps aufgelistet sind. Der **Bereich "Angeheftete Apps hinzufügen"** enthält nur Apps, die über eine Richtlinie an Teams angeheftet werden können.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein Teams für Education-Administrator. Was muss ich über App-Setuprichtlinien in Teams für Education wissen

Die Anruf-App ist in Teams für Education nicht verfügbar. Wenn Sie eine neue benutzerdefinierte App-Setuprichtlinie erstellen, wird die aufrufende App in der Liste der Apps angezeigt. Die App ist jedoch nicht an Teams-Clients angeheftet, und Teams für Education Benutzer die Anruf-App in Teams nicht sehen.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Wie viele angeheftete Apps einer Richtlinie hinzugefügt werden können

Mindestens zwei Apps müssen an die mobilen Teams-Clients (iOS und Android) angeheftet sein. Wenn eine Richtlinie weniger als zwei Apps enthält, spiegeln die mobilen Clients nicht die Richtlinieneinstellungen wider und verwenden stattdessen weiterhin die vorhandene Konfiguration.

Die Anzahl der angehefteten Apps, die Sie einer Richtlinie hinzufügen können, ist nicht begrenzt.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden?

Nach Bearbeiten oder Zuweisen einer Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle angehefteten Apps in Teams anzeigen?

Um alle Apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen Benutzer abhängig von der Anzahl der installierten Apps und der Größe ihres Teams-Clientfensters möglicherweise Folgendes tun.

|Microsoft Teams-Desktopclient |Mobile Microsoft Teams-Clients |
|---------|---------|
|Wählen Sie in der App-Leiste auf der Seite von Teams **... Weitere Apps**.| Wischen Sie in der App-Leiste am unteren Rand von Teams nach oben.|
|![Weitere Apps im Teams-Desktopclient.](media/app-setup-policies-desktop-more-apps.png)   |![weitere Apps im mobilen Microsoft Teams-Client](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die mobile Teams-Erfahrung wissen?

Die mobilen Teams-Clients (iOS und Android) unterstützen persönliche Apps mit statischen Registerkarten. An den Teams-Desktopclient angeheftete Apps werden in den mobilen Teams-Clients angezeigt. Persönliche Bots werden im Chat auf mobilen Clients angezeigt.

Drittanbieter-Apps (die aus dem Teams Store heruntergeladen werden können) müssen genehmigt werden, bevor sie auf mobilgeräten angezeigt werden. Wenn ein Administrator eine App anheftet, die von Microsoft für Mobile nicht genehmigt wird, wird sie auf dem Teams-Desktop angezeigt, aber nicht auf mobilen Geräten. Weitere Informationen finden Sie unter [Mobile Clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients).

Mit den mobilen Teams-Clients sehen Benutzer kernige Teams-Apps wie Aktivität, Chat und Teams, und Sie können einige Erstanbieter-Apps von Microsoft anheften, z. B. Schichten.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge von Apps ändern, die über eine Richtlinie angeheftet sind

Benutzer können die Reihenfolge ihrer angehefteten Apps auf Teams-Desktop- und mobilen Clients ändern, wenn die Option zum **Anheften von Benutzern** aktiviert ist. Benutzer können die Reihenfolge ihrer angehefteten Apps auf Teams-Webclients nicht ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften von Benutzern Vorrang

Admin Pins haben immer Vorrang. Wenn die Option zum **Anheften von** Benutzern aktiviert ist, behalten benutzer ihre angehefteten Apps unter den vom Administrator angehefteten Apps bei. Wenn die Option zum **Anheften von** Benutzern deaktiviert ist, verlieren Benutzer ihre bereits vorhandenen Pins, und nur von Administratoren angeheftete Apps sind in der App-Leiste vorhanden.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-Apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und veröffentlicht, entweder in AppSource oder im Mandanten-App-Katalog, aber das App-Symbol wird nicht wie erwartet angezeigt, wenn die App an die App-Leiste in Teams angeheftet ist. Gewusst wie beheben?

Stellen Sie sicher, dass Sie die Logorichtlinien befolgen, bevor Sie die App übermitteln. Weitere Informationen finden Sie unter [Checkliste für die Übermittlung an das Verkäuferdashboard](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="see-also"></a>Siehe auch

* [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
* [Zuweisen von Richtlinien zu Endbenutzern in Teams](assign-policies-users-and-groups.md)
