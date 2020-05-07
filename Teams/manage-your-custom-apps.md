---
title: Verwalten Ihrer benutzerdefinierten apps in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre benutzerdefinierten Teams-apps von der Entwicklung zur Bereitstellung bringen.
ms.openlocfilehash: a2896a2aa2b2d9750afd147b113a76637514afb6
ms.sourcegitcommit: b5c747e2daad6dd3c1d91f4e61ae6f26db5c77f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064530"
---
# <a name="manage-your-custom-apps-in-microsoft-teams"></a>Verwalten Ihrer benutzerdefinierten apps in Microsoft Teams

Dieser Artikel enthält eine umfassende Anleitung, wie Sie Ihre Teams-APP von der Entwicklung zur Bereitstellung führen können. Dieser Leitfaden konzentriert sich auf die Team Aspekte der APP und ist für IT-Experten vorgesehen. Weitere Informationen zum Entwickeln von Teams-apps finden Sie <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">hier</a>.

![Übersicht über Ihre APP von der Entwicklung bis zur Bereitstellung](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>Erste Schritte

Zum Erstellen und Verwalten benutzerdefinierter apps in Teams benötigen Sie zwei Mandanten: einen Testmandanten für die Entwicklung und einen Produktions Mandanten.

> [!NOTE]
> Wenn Sie noch nicht über einen Testmandanten verfügen, können Sie mit dem Office 365-Entwicklerprogramm schnell eins erstellen und es mit Testdaten füllen. <a href="https://developer.microsoft.com/office/dev-program" target="_blank">Weitere Informationen finden Sie hier</a>.

## <a name="step-1-develop-and-test"></a>Schritt 1: entwickeln und testen

### <a name="create-test-users"></a>Erstellen von Testbenutzern

Stellen Sie sicher, dass Ihre Entwickler, ob intern oder extern, über Konten in Ihrem Testmandanten verfügen. <a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">Weitere Informationen zum Hinzufügen von Benutzern</a>.

### <a name="allow-custom-apps-in-the-test-tenant"></a>Zulassen von benutzerdefinierten apps im Testmandanten

Damit Entwickler den Zugriff haben, den Sie für Tests benötigen, können Sie allen Benutzern im Testmandanten ermöglichen, benutzerdefinierte Apps (auch bekannt als Sideloading) hochzuladen. Auf diese Weise können Entwickler eine benutzerdefinierte App hochladen, um Sie persönlich oder über den Testmandanten zu verwenden, ohne die APP an den Team-Apps-Store übermitteln zu müssen. Beim Hochladen einer benutzerdefinierten App können Entwickler eine APP testen, bevor Sie Sie weiter verbreiten.

Führen Sie die folgenden Schritte aus, um Benutzern das Hochladen benutzerdefinierter apps zu ermöglichen:

1. Aktivieren Sie die Einstellung **Interaktion mit benutzerdefinierten apps in** der organisationsweiten App zulassen. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams Admin Center</a>zu **Teams apps** > **Verwalten von apps**, und klicken Sie dann auf **organisationsweite App-Einstellungen**.
    2. Aktivieren Sie unter **benutzerdefinierte apps**die Option **Interaktion mit benutzerdefinierten apps zulassen**, und klicken Sie dann auf **Speichern**.

    ![Screenshot der organisationsweiten app-Einstellung "Interaktion mit benutzerdefinierten apps zulassen"](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. Aktivieren Sie die Einstellung **benutzerdefinierte apps hochladen** in der globalen App-Setup Richtlinie. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams Admin Center</a>zu den**Setup Richtlinien**für **Teams-apps** > , und klicken Sie dann auf die **globale (org-Wide Standard)-** Richtlinie.
    2. Aktivieren Sie **benutzerdefinierte apps hochladen**, und klicken Sie dann auf **Speichern**.

    ![Screenshot der Richtlinieneinstellung "benutzerdefinierte apps hochladen" für die APP](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> Es gibt auch die Einstellung "benutzerdefinierte App hochladen" auf Team Ebene. Diese Einstellung ist standardmäßig aktiviert. Wenn Entwickler jedoch keine benutzerdefinierte app in ein Team hochladen können, überprüfen Sie die Einstellungen, indem Sie die <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">folgenden Schritte ausführen</a>.

### <a name="create-your-app"></a>Erstellen Ihrer APP

Entwickler sollten nun über die erforderlichen Elemente verfügen, um Ihre APP zu erstellen. <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Hier</a> finden Sie Anleitungen dazu.

## <a name="step-2-validate-in-production"></a>Schritt 2: Überprüfen in der Produktion

### <a name="get-the-app-package"></a>Abrufen des App-Pakets

Wenn die APP für die Verwendung in der Produktion bereit ist, sollte der Entwickler ein App-Paket erstellen. Sie können dafür <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> verwenden. Sie senden Ihnen die Datei im ZIP-Format.

Microsoft verwendet <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">Diese Richtlinien</a> , um sicherzustellen, dass apps den Qualitäts-und Sicherheitsstandards des globalen Teams Apps Store entsprechen.

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>Zulassen, dass vertrauenswürdige Benutzer benutzerdefinierte apps im Produktions Mandanten hochladen

Um zu überprüfen, ob die app in Ihrem Produktions Mandanten ordnungsgemäß funktioniert, müssen Sie sich selbst und/oder vertrauenswürdigen Benutzern in Ihrer Organisation erlauben, benutzerdefinierte apps hochzuladen.  Ähnlich wie im vorherigen <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">Schritt</a>verwenden Sie dazu die APP-Setup Richtlinien.

> [!NOTE]
> Wenn es Ihnen unangenehm ist, die APP für die Überprüfung an Ihren Produktions Mandanten zu überprüfen, auch für sich selbst oder für vertrauenswürdige Benutzer, können Sie diesen Schritt überspringen und die Schritte 3 und 4 ausführen, um die nicht validierte app in ihren Mandanten-App-Store hochzuladen. Dann beschränken Sie den Zugriff auf diese APP nur auf sich selbst und auf Benutzer, denen Sie vertrauen. Diese Benutzer können dann die APP aus dem Mandanten-App Store abrufen, um eine Validierung durchzuführen. Verwenden Sie nach der Überprüfung der APP dieselben Berechtigungsrichtlinien, um Access zu öffnen und die APP für die Produktion zu verwenden.

Führen Sie die folgenden Schritte aus, um vertrauenswürdigen Benutzern das Hochladen benutzerdefinierter apps zu ermöglichen:

1. Aktivieren Sie die Einstellung **Interaktion mit benutzerdefinierten apps in** der organisationsweiten App zulassen. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams Admin Center</a>zu **Teams apps** > **Verwalten von apps**, und klicken Sie dann auf **organisationsweite App-Einstellungen**.
    2. Aktivieren Sie unter **benutzerdefinierte apps**die Option **Interaktion mit benutzerdefinierten apps zulassen**, und klicken Sie dann auf **Speichern**.
2. Deaktivieren Sie die Einstellung **benutzerdefinierte apps hochladen** in der globalen App-Setup Richtlinie. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams Admin Center</a>zu den**Setup Richtlinien**für **Teams-apps** > , und klicken Sie dann auf die **globale (org-Wide Standard)-** Richtlinie.
    2. Deaktivieren Sie **benutzerdefinierte apps hochladen**, und klicken Sie dann auf **Speichern**.
3. Erstellen Sie eine neue Richtlinie für die APP-Einrichtung, die das Hochladen benutzerdefinierter apps und die Zuweisung an Ihre vertrauenswürdigen Benutzer ermöglicht. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams Admin Center</a>zu den**Setup Richtlinien**für **Teams-apps** > , und klicken Sie dann auf **Hinzufügen**. Geben Sie der neuen Richtlinie einen Namen und eine Beschreibung, aktivieren Sie **benutzerdefinierte apps hochladen**, und klicken Sie dann auf **Speichern**.
    2. Wählen Sie die neu erstellte Richtlinie aus, und klicken Sie dann auf **Benutzer verwalten**. Suchen Sie nach einem Benutzer, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf über **nehmen**. Wiederholen Sie diesen Schritt, um die Richtlinie allen vertrauenswürdigen Benutzern zuzuweisen.

        ![Screenshot der Seite "App-Setup Richtlinie hinzufügen"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Diese Benutzer können jetzt das App-Manifest hochladen, um zu überprüfen, ob die APP im Produktions Mandanten ordnungsgemäß funktioniert.

## <a name="step-3-upload-to-the-tenant-app-catalog"></a>Schritt 3: Hochladen in den Mandanten-App-Katalog

Wenn Sie die APP für Benutzer im Mandanten-App-Store verfügbar machen möchten, laden Sie die APP hoch. Sie können dies auf der Seite " [apps verwalten](manage-apps.md) " im Microsoft Teams Admin Center tun.

![Screenshot der Seite "Apps verwalten" im Admin Center](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a>Schritt 4: Konfigurieren und Zuweisen von Berechtigungen

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die APP

Standardmäßig haben alle Benutzer Zugriff auf diese APP im Store für Teams-apps. Um zu beschränken und zu steuern, wer die Berechtigung zum Verwenden der APP hat, können Sie eine neue APP-Berechtigungsrichtlinie erstellen und zuweisen. Führen Sie die <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">folgenden Schritte aus</a>.

![Screenshot der Seite "App-Berechtigungsrichtlinie hinzufügen"](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>Anheften der APP für Benutzer zum Ermitteln

Standardmäßig müssten die Benutzer diese APP finden, wenn Sie zu den Apps für Teams wechseln müssten, um Sie zu speichern und zu durchsuchen. Um Benutzern das Abrufen der APP zu erleichtern, können Sie die app in Teams an die APP-Leiste anheften. Erstellen Sie dazu eine neue APP-Setup Richtlinie, und weisen Sie Sie Benutzern zu. Führen Sie die <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">folgenden Schritte aus</a>.

![Screenshot des Bereichs "angeheftete apps hinzufügen"](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>Schritt 5: Aktualisieren der APP

![Übersicht über Ihre APP von der Entwicklung bis zur Bereitstellung](media/manage-your-lob-apps-update.png)

Um eine APP zu aktualisieren, sollten Entwickler weiterhin [Schritt 1](#step-1-develop-and-test) und [Schritt 2](#step-2-validate-in-production)folgen.

Sie können die APP über den Mandanten-App-Katalog aktualisieren. Gehen Sie dazu im Microsoft Teams Admin Center zu **Teams apps** > **Verwalten von apps**. Klicken Sie in der Liste der apps auf den Namen der APP, und klicken Sie dann auf **Aktualisieren**. Dadurch wird die vorhandene App im Mandanten-App-Katalog ersetzt, und alle App-Berechtigungsrichtlinien und Richtlinien für die APP-Einrichtung bleiben für die aktualisierte APP erzwungen.

### <a name="end-user-update-experience"></a>Benutzer-Update-Benutzeroberfläche

In den meisten Fällen wird die neue Version nach Abschluss eines APP-Updates automatisch für Endbenutzer angezeigt. Es gibt jedoch einige Updates für das <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams-Manifest</a> , für die eine Benutzerakzeptanz erforderlich ist:

* Ein bot wurde hinzugefügt oder entfernt
* Eine vorhandene bot-Eigenschaft "botId" wurde geändert
* Eine vorhandene bot-Eigenschaft "isNotificationOnly" wurde geändert
* Die "supportsFiles"-Eigenschaft des bot wurde geändert
* Eine Messaging Erweiterung wurde hinzugefügt oder entfernt
* Ein neuer Connector wurde hinzugefügt
* Eine neue statische Registerkarte wurde hinzugefügt
* Eine neue konfigurierbare Registerkarte wurde hinzugefügt
* Eigenschaften innerhalb von "webApplicationInfo" geändert

![Screenshot der Liste "Apps" mit apps, für die eine neue Version verfügbar ist](media/manage-your-custom-apps-update1.png)

![Screenshot der Upgrade-Option für eine APP](media/manage-your-custom-apps-update2.png)

## <a name="related-apps"></a>Verwandte apps

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
