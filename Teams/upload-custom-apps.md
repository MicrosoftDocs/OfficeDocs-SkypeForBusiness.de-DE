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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre benutzerdefinierten Apps im Microsoft Teams Admin Center in den App Store Ihrer Organisation hochladen.
ms.openlocfilehash: 9473c8e2fc4284c4ca205666152ef183b0210841
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115523"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Verwendung hängt davon ab, wie Sie die App erhalten. Dieser Artikel befasst sich mit dem Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets **(im ZIP-Format),** das Ihnen von einem Entwickler übermittelt wird. Die andere Methode, die Genehmigung einer benutzerdefinierten App, wird <a href="/microsoftteams/manage-apps" target="_blank"></a> verwendet, wenn ein Entwickler eine App über die Teams App Submission API direkt an die Seite Apps verwalten sendet. Weitere Informationen zu dieser Methode finden Sie unter Veröffentlichen einer benutzerdefinierten App, die über <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">die Teams App Submission API übermittelt wurde.</a>

Dieser Artikel enthält eine end-to-end-Anleitung, wie Sie Ihre Teams-App von der Entwicklung über die Bereitstellung bis zur Discovery verwenden. Dieser Leitfaden konzentriert sich auf die Teams-Aspekte der App und richtet sich an Administratoren und IT-Profis. Weitere Informationen zum Entwickeln von Teams-Apps finden Sie in der <a href="/microsoftteams/platform" target="_blank">Dokumentation zu Teams-Entwicklern.</a>

![Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung](media/upload-custom-apps.png)

## <a name="develop"></a>Entwickeln

### <a name="create-your-app"></a>Erstellen Ihrer App

Die Microsoft Teams-Entwicklerplattform erleichtert Entwicklern die Integration Eigener Apps und Dienste, um die Produktivität zu verbessern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu fördern. Apps, die auf der Teams-Plattform erstellt wurden, sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows und bringen sie direkt in den Kontext Ihrer Zusammenarbeitsplattform. Weitere Informationen finden Sie in der <a href="/microsoftteams/platform" target="_blank">Dokumentation zu Teams-Entwicklern.</a>

## <a name="validate"></a>Überprüfen

### <a name="get-the-app-package"></a>Herunterladen des App-Pakets

Wenn die App in der Produktion einsatzbereit ist, sollte der Entwickler ein App-Paket erstellen. Dafür können sie <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> verwenden. Sie senden Ihnen die Datei im ZIP-Format.

Microsoft verwendet <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">diese Richtlinien,</a> um sicherzustellen, dass Apps den Qualitäts- und Sicherheitsstandards des globalen Teams-Apps-Store entsprechen.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Zulassen, dass vertrauenswürdige Benutzer benutzerdefinierte Apps hochladen

Um zu überprüfen, ob die App in Ihrem Produktions-Mandant ordnungsgemäß funktioniert, müssen Sie es sich und/oder vertrauenswürdigen Benutzern erlauben, benutzerdefinierte Apps in den Produktions mandanten hochzuladen. Dazu verwenden <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Sie App-Setuprichtlinien.</a>

> [!NOTE]
> Wenn Sie nicht getraut haben, die App zur Überprüfung in Ihren Produktions mandanten hochzuladen, auch [](#upload) für [](#set-up-and-manage) sich selbst oder vertrauenswürdige Benutzer, können Sie diesen Schritt überspringen und die Schritte in den Abschnitten Hochladen und Einrichten und Verwalten ausführen, um die nicht validierte App im App Store Ihrer Organisation zu veröffentlichen. Beschränken Sie dann den Zugriff auf diese App nur auf sich selbst und benutzer, dem Sie vertrauen. Diese Benutzer können die App dann aus dem App Store Ihrer Organisation holen, um die Überprüfung durchzuführen. Nachdem die App überprüft wurde, verwenden Sie dieselben Berechtigungsrichtlinien, um den Zugriff zu öffnen und die App für die Produktionsnutzung zu rollouten.

Führen Sie die folgenden Schritte aus, um vertrauenswürdigen Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen:

1. Aktivieren Sie die **Organisationsweite** App-Einstellung Interaktion mit benutzerdefinierten Apps zulassen. Gehen Sie dazu so vor:
    1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams-Apps** Apps verwalten, und klicken Sie dann  >  auf **Organisationsweite App-Einstellungen.**
    2. Aktivieren **Sie unter Benutzerdefinierte Apps** die Schaltfläche Interaktion mit benutzerdefinierten Apps **zulassen,** und klicken Sie dann auf **Speichern.**
2. Deaktivieren Sie die **Einstellung Benutzerdefinierte Apps hochladen** in der globalen App-Setuprichtlinie. Gehen Sie dazu so vor:
    1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Richtlinien** für die Einrichtung von Teams-Apps, und klicken Sie dann auf die Richtlinie  >   **Global (Organisationsweite** Standardrichtlinie).
    2. Deaktivieren Sie **Benutzerdefinierte Apps hochladen,** und klicken Sie dann auf **Speichern.**
3. Erstellen Sie eine neue App-Setuprichtlinie, die das Hochladen benutzerdefinierter Apps ermöglicht, und weisen Sie sie Ihren vertrauenswürdigen Benutzern zu. Gehen Sie dazu so vor:
    1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu Setuprichtlinien für **Teams-Apps,** und klicken Sie  >  dann auf **Hinzufügen.** Geben Sie der neuen Richtlinie einen Namen und eine Beschreibung, aktivieren Sie **benutzerdefinierte Apps hochladen,** und klicken Sie dann auf **Speichern.**
    2. Wählen Sie die neue Richtlinie aus, die Sie erstellt haben, und klicken Sie dann **auf Benutzer verwalten.** Suchen Sie nach einem Benutzer, klicken **Sie auf Hinzufügen**, und klicken Sie dann auf **Übernehmen.** Wiederholen Sie diesen Schritt, um die Richtlinie allen vertrauenswürdigen Benutzern zuzuordnen.

        ![Screenshot der Seite "App-Setuprichtlinie hinzufügen"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Diese Benutzer können jetzt das App-Manifest hochladen, um zu überprüfen, ob die App im Produktions-Mandant ordnungsgemäß funktioniert.

## <a name="upload"></a>Hochladen

Laden Sie die App hoch, um die App benutzern im App Store Ihrer Organisation zur Verfügung zu stellen. Dies können Sie auf der Seite <a href="/microsoftteams/manage-apps" target="_blank">Apps</a> verwalten im Microsoft Teams Admin Center tun.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken **Sie auf Hochladen,** klicken Sie auf Datei **auswählen,** und wählen Sie dann das App-Paket aus, das Sie vom Entwickler erhalten haben.

   ![Screenshot des Hochladens einer App im Admin Center](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Einrichten und Verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die App

Standardmäßig können alle Benutzer in Ihrer Organisation im App Store Ihrer Organisation auf die App zugreifen. Zum Einschränken und Steuern, wer über die Berechtigung zur Verwendung der App verfügt, können Sie eine App-Berechtigungsrichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der App für Benutzer

Standardmäßig müssen Benutzer die App suchen, die sie haben, zum App Store Ihrer Organisation wechseln und sie durchsuchen oder suchen. Um Benutzern den Zugriff auf die App zu ermöglichen, können Sie die App in Teams an die App-Leiste anheften. Erstellen Sie dazu eine App-Setuprichtlinie, und weisen Sie sie Benutzern zu. Weitere Informationen finden Sie unter <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Durchsuchen des Überwachungsprotokolls nach Teams-App-Ereignissen

Sie können das Überwachungsprotokoll durchsuchen, um die Aktivitäten von Teams-Apps in Ihrer Organisation anzeigen zu können. Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Sehen einer Liste der im Überwachungsprotokoll protokollierten Teams-Aktivitäten finden Sie unter Durchsuchen des Überwachungsprotokolls nach Ereignissen <a href="/microsoftteams/audit-log-events" target="_blank">in Teams.</a>

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a> die Überwachung aktivieren. Weitere Informationen finden Sie unter <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Die Überwachungsprotokollsuche ein- oder ausschalten</a>. Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="discover-and-adopt"></a>Entdecken und Übernehmen

Benutzer, die über Berechtigungen für die App verfügen, können sie im App Store Ihrer Organisation finden. Wechseln Sie auf der Seite Apps zu Erstellt für ***Ihren*** Organisationsnamen, um die benutzerdefinierten Apps Ihrer Organisation zu finden.

![Screenshot der Seite "Apps" mit veröffentlichter App ](media/custom-app-lifecycle-discovery.png)

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um den Benutzern, denen die Richtlinie zugewiesen wurde, einfachen Zugriff zu ermöglichen.

## <a name="update"></a>Aktualisieren

Zum Aktualisieren einer App sollten Entwickler weiterhin die Schritte in den Abschnitten [Entwickeln](#develop) und [Überprüfen](#validate) ausführen.

Sie können die App auf der Seite Apps verwalten im Microsoft Teams Admin Center aktualisieren. Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps**  >  **Apps verwalten.** Klicken Sie auf den Namen der App, und klicken Sie dann auf **Aktualisieren.** Dadurch wird die vorhandene App ersetzt, und alle Richtlinien für App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

### <a name="end-user-update-experience"></a>Updateerfahrung für Endbenutzer

In den meisten Fällen wird die neue Version nach Abschluss eines App-Updates automatisch für Endbenutzer angezeigt. Es gibt jedoch einige Updates für das <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams-Manifest,</a> für die die Benutzerakzeptanz erforderlich ist:

* Ein Bot wurde hinzugefügt oder entfernt
* Die "botId"-Eigenschaft eines vorhandenen Bots wurde geändert
* Die Eigenschaft "isNotificationOnly" eines vorhandenen Bots wurde geändert
* Die Eigenschaft "supportsFiles" des Bots wurde geändert
* Eine Messagingerweiterung wurde hinzugefügt oder entfernt
* Ein neuer Verbinder wurde hinzugefügt
* Eine neue statische Registerkarte wurde hinzugefügt
* Eine neue konfigurierbare Registerkarte wurde hinzugefügt
* Eigenschaften in "webApplicationInfo" geändert

![Screenshot der Liste der Apps mit Apps, für die eine neue Version verfügbar ist](media/manage-your-custom-apps-update1.png)

![Screenshot der Upgradeoption für eine App](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Verwandte Themen

- [Veröffentlichen einer benutzerdefinierten App, die über die Übermittlungs-API für Teams-Apps übermittelt wird](submit-approve-custom-apps.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)