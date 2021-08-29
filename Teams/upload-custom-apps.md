---
title: Hochladen Ihrer benutzerdefinierten Apps im Microsoft Teams Admin Center
author: cichur
ms.author: v-cichur
manager: serdars
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
description: Erfahren Sie, wie Sie Ihre benutzerdefinierten Apps in den App Store Ihrer Organisation im Admin Microsoft Teams Admin Center hochladen.
ms.openlocfilehash: 2e5eecc0bb5f5ed7c03552057cca6d42f7395ca2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634699"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art der Verwendung hängt davon ab, wie Sie die App erhalten. Dieser Artikel befasst sich mit dem Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets **(im .zip-Format),** das Ihnen von einem Entwickler übermittelt wird. Die andere Methode, die Genehmigung einer benutzerdefinierten App, wird <a href="/microsoftteams/manage-apps" target="_blank"></a> verwendet, wenn ein Entwickler eine App über die APP-Einreichungs-API direkt an die Seite Apps verwalten Teams übermittelt. Weitere Informationen zu dieser Methode finden Sie unter Veröffentlichen einer benutzerdefinierten App, die über die <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">APP Teams Übermittlungs-API übermittelt wird.</a>

Dieser Artikel enthält eine End-to-End-Anleitung, wie Sie Ihre Teams von der Entwicklung über die Bereitstellung bis zur Ermittlung weiterverhilfen können. Dieser Leitfaden befasst sich Teams Aspekte der App und richtet sich an Administratoren und IT-Profis. Weitere Informationen zum Entwickeln von Teams-Apps finden Sie in der <a href="/microsoftteams/platform" target="_blank">Teams für Entwickler.</a>

![Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung](media/upload-custom-apps.png)

## <a name="develop"></a>Entwickeln

### <a name="create-your-app"></a>Erstellen Ihrer App

Die Microsoft Teams-Entwicklerplattform erleichtert Entwicklern die Integration Ihrer eigenen Apps und Dienste, um die Produktivität zu steigern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu fördern. Apps, die auf der Teams-Plattform erstellt wurden, sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows und bringen sie direkt in den Kontext Ihrer Zusammenarbeitsplattform. Weitere Informationen finden Sie in der Dokumentation <a href="/microsoftteams/platform" target="_blank">Teams Entwickler.</a>

## <a name="validate"></a>Überprüfen

### <a name="get-the-app-package"></a>Herunterladen des App-Pakets

Wenn die App für die Produktion bereit ist, sollte der Entwickler ein App-Paket erstellen. Dazu können sie <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> verwenden. Sie senden Ihnen die Datei im .zip Format.

Microsoft verwendet <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">diese Richtlinien,</a> um sicherzustellen, dass Apps den Qualitäts- und Sicherheitsstandards der globalen App-Teams entsprechen.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Zulassen, dass vertrauenswürdige Benutzer benutzerdefinierte Apps hochladen

Um zu überprüfen, ob die App in Ihrem Produktions-Mandanten ordnungsgemäß funktioniert, müssen Sie es sich selbst und/oder vertrauenswürdigen Benutzern gestatten, benutzerdefinierte Apps in den Produktions-Mandanten hochzuladen. Dazu verwenden <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Sie App-Setuprichtlinien.</a>

> [!NOTE]
> Wenn Sie unsicher sind, die App zur Überprüfung in Ihren Produktions-Mandanten hochzuladen, auch für Sich selbst oder [](#set-up-and-manage) vertrauenswürdige Benutzer, können Sie diesen Schritt überspringen und die Schritte in den Abschnitten [Hochladen](#upload) und Einrichten und Verwalten ausführen, um die nichtvalidierte App im App Store Ihrer Organisation zu veröffentlichen. Schränken Sie den Zugriff auf diese App dann auf sich selbst und vertrauenswürdige Benutzer ein. Diese Benutzer können die App dann aus dem App Store Ihrer Organisation herunterladen, um die Überprüfung durchzuführen. Nachdem die App überprüft wurde, verwenden Sie dieselben Berechtigungsrichtlinien, um den Zugriff zu öffnen und die App für die Produktionsnutzung zu verwenden.

Führen Sie die folgenden Schritte aus, um vertrauenswürdigen Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen:

1. Aktivieren Sie die **Einstellung Interaktion mit benutzerdefinierten Apps** organisationsweit zulassen. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Teams Apps** Apps verwalten , und klicken Sie dann auf  >   **Organisationsweite App-Einstellungen**.
    2. Aktivieren **Sie unter** Benutzerdefinierte Apps die Schaltfläche Interaktion mit benutzerdefinierten Apps **zulassen**, und klicken Sie dann auf **Speichern.**
2. Deaktivieren Sie die Einstellung **Hochladen Benutzerdefinierten Apps** in der globalen App-Setuprichtlinie. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Richtlinien** für Apps einrichten , und klicken Sie dann auf die Richtlinie Global  >   **(Organisationsweite** Standardrichtlinie).
    2. Deaktivieren Sie **Hochladen Benutzerdefinierte Apps,** und klicken Sie dann auf **Speichern.**
3. Erstellen Sie eine neue App-Setuprichtlinie, die das Hochladen benutzerdefinierter Apps ermöglicht, und weisen Sie sie Ihren vertrauenswürdigen Benutzern zu. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für Teams Apps einrichten , und klicken  >  Sie dann auf **Hinzufügen**. Geben Sie der neuen Richtlinie einen Namen und eine Beschreibung, aktivieren Sie **Hochladen Benutzerdefinierte** Apps, und klicken Sie dann auf **Speichern.**
    2. Wählen Sie die neue Richtlinie aus, die Sie erstellt haben, und klicken Sie **dann auf Benutzer verwalten.** Suchen Sie nach einem Benutzer, klicken **Sie auf Hinzufügen**, und klicken Sie dann auf **Übernehmen**. Wiederholen Sie diesen Schritt, um die Richtlinie allen vertrauenswürdigen Benutzern zuzuordnen.

        ![Screenshot der Seite "App-Setuprichtlinie hinzufügen"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Diese Benutzer können nun das App-Manifest hochladen, um zu überprüfen, ob die App im Produktions-Mandanten ordnungsgemäß funktioniert.

## <a name="upload"></a>Hochladen

Um die App Benutzern im App Store Ihrer Organisation zur Verfügung zu stellen, laden Sie die App hoch. Sie können dies auf der <a href="/microsoftteams/manage-apps" target="_blank">Seite "Apps verwalten"</a> im Microsoft Teams Admin Center tun.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken **Hochladen**, klicken **Sie auf Datei auswählen**, und wählen Sie dann das App-Paket aus, das Sie vom Entwickler erhalten haben.

   ![Screenshot des Hochladens einer App im Admin Center](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Einrichten und Verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die App

Standardmäßig können alle Benutzer in Ihrer Organisation im App Store Ihrer Organisation auf die App zugreifen. Um einzuschränken und zu steuern, wer über die Berechtigung zum Verwenden der App verfügt, können Sie eine App-Berechtigungsrichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der App, die Benutzer entdecken können

Damit Benutzer die App finden können, die sie haben, müssen sie standardmäßig zum App Store Ihrer Organisation wechseln und nach der App suchen. Um Benutzern den Zugriff auf die App zu ermöglichen, können Sie die App an die App-Leiste in Teams. Erstellen Sie dazu eine App-Setuprichtlinie, und weisen Sie sie Benutzern zu. Weitere Informationen finden Sie unter <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Durchsuchen des Überwachungsprotokolls nach Teams App-Ereignissen

Sie können das Überwachungsprotokoll durchsuchen, um die Aktivitäten Teams Apps in Ihrer Organisation anzeigen. Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Sehen einer Liste der Teams-Aktivitäten, die im Überwachungsprotokoll protokolliert werden, finden Sie unter Durchsuchen des Überwachungsprotokolls nach Ereignissen <a href="/microsoftteams/audit-log-events" target="_blank">in Teams.</a>

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a> die Überwachung aktivieren. Weitere Informationen finden Sie unter <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Die Überwachungsprotokollsuche ein- oder ausschalten</a>. Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="discover-and-adopt"></a>Entdecken und Übernehmen

Benutzer mit Berechtigungen für die App finden sie im App Store Ihrer Organisation. Wechseln Sie auf der Seite Apps zu Für Ihre ***Organisation*** erstellt, um die benutzerdefinierten Apps Ihrer Organisation zu finden.

![Screenshot der Seite "Apps" mit veröffentlichter App ](media/custom-app-lifecycle-discovery.png)

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um den Zugriff für die Benutzer zu ermöglichen, denen die Richtlinie zugewiesen wurde.

## <a name="update"></a>Aktualisieren

Zum Aktualisieren einer App sollten Entwickler weiterhin die Schritte in den Abschnitten Entwickeln [und](#develop) [Überprüfen](#validate) ausführen.

Sie können die App auf der Seite Apps verwalten im Microsoft Teams Admin Center aktualisieren. Wechseln Sie dazu in der linken Navigationsleiste Microsoft Teams Admin Center zu Teams  >  **Apps verwalten**. Klicken Sie auf den App-Namen, und klicken Sie dann **auf Aktualisieren**. Dadurch wird die vorhandene App ersetzt, und alle Richtlinien für App-Berechtigungen und App-Setup bleiben für die aktualisierte App erhalten.

### <a name="end-user-update-experience"></a>Updateerfahrung für Endbenutzer

In den meisten Fällen wird nach Abschluss einer App-Aktualisierung die neue Version automatisch für Endbenutzer angezeigt. Es gibt jedoch einige Aktualisierungen des Manifests <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams,</a> die die Benutzerakzeptanz erfordern, um abgeschlossen zu werden:

* Ein Bot wurde hinzugefügt oder entfernt
* Die "botId"-Eigenschaft eines vorhandenen Bots wurde geändert
* Die IsNotificationOnly-Eigenschaft eines vorhandenen Bots wurde geändert
* Die Eigenschaft "supportsFiles" des Bots wurde geändert
* Eine Messaging-Erweiterung wurde hinzugefügt oder entfernt
* Ein neuer Connector wurde hinzugefügt
* Eine neue statische Registerkarte wurde hinzugefügt
* Eine neue konfigurierbare Registerkarte wurde hinzugefügt
* Eigenschaften in "webApplicationInfo" wurden geändert

![Screenshot der App-Liste mit Apps, für die eine neue Version verfügbar ist](media/manage-your-custom-apps-update1.png)

![Screenshot der Upgradeoption für eine App](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Verwandte Themen

- [Veröffentlichen einer benutzerdefinierten App, die über die APP Teams Übermittlungs-API übermittelt wird](submit-approve-custom-apps.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)