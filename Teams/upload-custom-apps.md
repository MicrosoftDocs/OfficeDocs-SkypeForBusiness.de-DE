---
title: Hochladen Ihrer benutzerdefinierten Apps im Microsoft Teams Admin Center
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: joglocke, vaibhava
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre benutzerdefinierten Apps im Microsoft Teams Admin Center in den App Store Ihrer Organisation hochladen.
ms.openlocfilehash: 8f7968a53b70ac8ffa871d03adacd648ec047c52
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958050"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art und Weise, wie Sie diese verwenden, hängt davon ab, wie Sie die App erhalten. **Dieser Artikel befasst sich mit dem Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets (in .zip Format), das Ihnen ein Entwickler sendet**. Die andere Methode, die Genehmigung einer benutzerdefinierten App, wird verwendet, wenn ein Entwickler eine App direkt über die Teams-App-Übermittlungs-API an die Seite " [Apps verwalten"](manage-apps.md) übermittelt. Weitere Informationen zu dieser Methode finden Sie unter [Veröffentlichen einer benutzerdefinierten App, die über die Teams-App-Übermittlungs-API übermittelt wurde](submit-approve-custom-apps.md).

Dieser Artikel enthält end-to-end-Anleitungen, wie Sie Ihre Teams-App von der Entwicklung über die Bereitstellung bis hin zur Ermittlung nutzen können. Dieser Leitfaden konzentriert sich auf die Teams-Aspekte der App und richtet sich an Administratoren und IT-Experten. Weitere Informationen zum Entwickeln von Teams-Apps finden Sie in der [Teams-Entwicklerdokumentation](/microsoftteams/platform/).

![Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung.](media/upload-custom-apps.png)

## <a name="create-your-app"></a>Erstellen Ihrer App

Die Microsoft Teams-Entwicklerplattform macht es Entwicklern leicht, Ihre eigenen Apps und Dienste zu integrieren, um die Produktivität zu verbessern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu erstellen. Auf der Teams-Plattform erstellte Apps sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows, die sie direkt in den Kontext Ihrer Plattform für die Zusammenarbeit bringen. Weitere Informationen finden Sie in der [Teams-Entwicklerdokumentation](/microsoftteams/platform/).

## <a name="validate"></a>Überprüfen

### <a name="get-the-app-package"></a>Abrufen des App-Pakets

Wenn die App für die Verwendung in der Produktion bereit ist, sollte der Entwickler ein App-Paket erstellen. Sie können [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview) verwenden. Sie senden Ihnen die Datei im .zip Format.

Alle Apps im Teams Store bestehen eine obligatorische [App-Überprüfung](overview-of-app-validation.md) , um die Qualitäts- und Sicherheitsstandards des globalen Teams-Apps-Stores zu erfüllen. Darüber hinaus empfiehlt Microsoft App-Entwicklern dringend, an einem optionalen [App-Complianceprogramm](overview-of-app-certification.md) teilzunehmen, das erweiterte Compliance-, Sicherheits- und Datenschutzkontrollen angibt. Weitere Informationen finden Sie unter [Teams-App-Validierungsrichtlinien](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Zulassen, dass vertrauenswürdige Benutzer benutzerdefinierte Apps hochladen

Um zu überprüfen, ob die App in Ihrem Produktionsmandanten ordnungsgemäß funktioniert, müssen Sie es ihnen und/oder vertrauenswürdigen Benutzern ermöglichen, benutzerdefinierte Apps in den Produktionsmandanten hochzuladen. Dazu verwenden Sie [App-Setuprichtlinien](teams-app-setup-policies.md) .

> [!NOTE]
> Wenn Sie die App zur Überprüfung in Ihren Produktionsmandanten hochladen möchten, selbst für sich selbst oder vertrauenswürdige Benutzer, können Sie diesen Schritt überspringen und die Schritte in den Abschnitten ["Hochladen](#upload) " und ["Einrichten und Verwalten](#set-up-and-manage) " ausführen, um die nicht überprüfte App im App Store Ihrer Organisation zu veröffentlichen. Beschränken Sie dann den Zugriff auf diese App auf sich selbst und die Benutzer, denen Sie vertrauen. Diese Benutzer können dann die App aus dem App Store Ihrer Organisation abrufen, um eine Überprüfung durchzuführen. Nachdem die App überprüft wurde, verwenden Sie die gleichen Berechtigungsrichtlinien, um den Zugriff zu öffnen und die App für die Produktionsverwendung einzusetzen.

Führen Sie die folgenden Schritte aus, um vertrauenswürdigen Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen:

1. Aktivieren Sie die Einstellung **"Interaktion mit benutzerdefinierten Apps** organisationsweit zulassen". Gehen Sie dazu so vor:

    1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **"Teams-Apps** > **verwalten**", und klicken Sie dann auf " **Organisationsweite App-Einstellungen"**.

    1. Aktivieren Sie unter **"Benutzerdefinierte Apps**" die Option **"Interaktion mit benutzerdefinierten Apps zulassen**", und klicken Sie dann auf **"Speichern"**.

1. Deaktivieren Sie die Einstellung " **Benutzerdefinierte Apps hochladen** " in der globalen App-Setuprichtlinie. Gehen Sie dazu so vor:

    1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu den **Setuprichtlinien** für **Teams-Apps** > , und klicken Sie dann auf die **globale Richtlinie (organisationsweite Standardrichtlinie**).

    1. Deaktivieren Sie **"Benutzerdefinierte Apps hochladen**", und klicken Sie dann auf **"Speichern"**.

1. Erstellen Sie eine neue App-Setuprichtlinie, die das Hochladen benutzerdefinierter Apps ermöglicht, und weisen Sie sie Ihren vertrauenswürdigen Benutzern zu. Gehen Sie dazu so vor:

    1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu den **Setuprichtlinien** für **Teams-Apps** > , und klicken Sie dann auf "**Hinzufügen"**. Geben Sie der neuen Richtlinie einen Namen und eine Beschreibung, aktivieren **Sie "Benutzerdefinierte Apps hochladen**", und klicken Sie dann auf **"Speichern"**.

    1. Wählen Sie die neue Richtlinie aus, die Sie erstellt haben, und klicken Sie dann auf **"Benutzer verwalten**". Suchen Sie nach einem Benutzer, klicken Sie auf **"Hinzufügen"** und dann auf **"Übernehmen**". Wiederholen Sie diesen Schritt, um die Richtlinie allen vertrauenswürdigen Benutzern zuzuweisen.

       ![Screenshot der Seite "App-Setuprichtlinie hinzufügen"](media/manage-your-lob-apps-new-app-setup-policy.png)

Diese Benutzer können nun das App-Manifest hochladen, um zu überprüfen, ob die App im Produktionsmandanten ordnungsgemäß funktioniert.

## <a name="upload"></a>Hochladen

Um die App für Benutzer im App Store Ihrer Organisation verfügbar zu machen, laden Sie die App hoch.

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu "Apps **[verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**" in **Teams-Apps** > .
1. Wählen Sie **"Hochladen**" aus, klicken Sie auf **"Hochladen**", wählen Sie das App-Paket aus, das Sie vom Entwickler erhalten haben, und wählen Sie **"Öffnen**" aus.

   ![Screenshot des Hochladens einer App im Admin Center.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Einrichten und Verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die App

Standardmäßig können alle Benutzer in Ihrer Organisation auf die App im App Store Ihrer Organisation zugreifen. Um einzuschränken und zu steuern, wer über die Berechtigung zur Verwendung der App verfügt, können Sie eine App-Berechtigungsrichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der app für Benutzer zu entdecken

Wenn Benutzer die App suchen möchten, müssen sie standardmäßig zum App Store Ihrer Organisation wechseln und danach suchen oder suchen. Um Benutzern den Zugriff auf die App zu erleichtern, können Sie die App an die App-Leiste in Teams anheften. Erstellen Sie dazu eine App-Setuprichtlinie, und weisen Sie sie Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Durchsuchen des Überwachungsprotokolls nach Teams-App-Ereignissen

Sie können das Überwachungsprotokoll durchsuchen, um die Aktivitäten von Teams-Apps in Ihrer Organisation anzuzeigen. Weitere Informationen zur Überwachung von Teams-Aktivitäten finden Sie [im Überwachungsprotokoll nach Ereignissen in Teams](audit-app-management-activities.md).

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im [Security & Compliance Center](https://sip.protection.office.com/homepage) die Überwachung aktivieren. Weitere Informationen finden Sie unter [Die Überwachungsprotokollsuche ein- oder ausschalten](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="discover-and-adopt"></a>Entdecken und einführen

Endbenutzer, die über Berechtigungen für die App verfügen, können sie im App Store Ihrer Organisation finden. Wechseln Sie auf der Seite "Apps" zu ***"Für Ihre Organisation* erstellter Name**", um die benutzerdefinierten Apps Ihrer Organisation zu finden.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Screenshot des Teams-Stores mit der für die Organisation veröffentlichten benutzerdefinierten App" lightbox="media/custom-app-lifecycle-discovery.png":::

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um für benutzer, denen die Richtlinie zugewiesen wurde, einfachen Zugriff zu erhalten.

## <a name="update"></a>Aktualisieren

Zum Aktualisieren einer App führen Entwickler die Schritte in den Abschnitten ["App erstellen](#create-your-app) " und ["Überprüfen"](#validate) aus.

Sie können die App auf der Seite "Apps verwalten" im Microsoft Teams Admin Center aktualisieren. Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Centers zu "Apps **verwalten**" für **Teams-Apps** > . Klicken Sie auf den App-Namen und dann auf **"Aktualisieren**". Dadurch wird die vorhandene App ersetzt, und alle App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

### <a name="end-user-update-experience"></a>Endbenutzeraktualisierungserfahrung

In den meisten Fällen wird die neue Version nach Abschluss einer App-Aktualisierung automatisch für Endbenutzer angezeigt. Weitere Informationen finden Sie in der [Updateumgebung für Endbenutzer](apps-update-experience.md).

## <a name="remove"></a>Entfernen

Führen Sie die folgenden Schritte aus, um eine App zu entfernen:

1. Melden Sie sich beim Microsoft Teams Admin Center an.
1. Seite "Apps **[verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**" auf **Teams-Apps** >  zugreifen.
1. Klicken Sie auf den Namen der App, um die Seite mit den App-Details zu öffnen.
1. Wählen Sie neben dem App-Banner **"Aktionen löschen"** > **aus**.
1. Wählen Sie im Dialogfeld " **Löschen**" aus.

## <a name="related-articles"></a>Verwandte Artikel

* [Veröffentlichen einer benutzerdefinierten App, die über die Teams-App-Übermittlungs-API übermittelt wurde](submit-approve-custom-apps.md)
* [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
* [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
* [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
* [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
