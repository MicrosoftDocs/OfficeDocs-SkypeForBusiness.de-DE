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
ms.openlocfilehash: f1b5267fe1003d69c0d91349f5b6bc425df2b038
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831165"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art und Weise, wie Sie sie verwenden, hängt davon ab, wie Sie die App erhalten. Dieser Artikel befasst sich mit dem Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets **(im ZIP-Format),** das Ihnen ein Entwickler sendet. Die andere Methode, die Genehmigung einer benutzerdefinierten App, wird <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> verwendet, wenn ein Entwickler eine App über die Übermittlungs-API für Teams-Apps direkt an die Seite "Apps verwalten" übermittelt. Weitere Informationen zu dieser Methode finden Sie unter "Veröffentlichen einer benutzerdefinierten App, die über die <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Übermittlungs-API für Teams-Apps übermittelt wird".</a>

Dieser Artikel enthält eine End-to-End-Anleitung, wie Sie Ihre Teams-App von der Entwicklung über die Bereitstellung bis zur Ermittlung weiterverbauen können. Dieser Leitfaden konzentriert sich auf die Aspekte von Teams der App und richtet sich an Administratoren und IT-Profis. Weitere Informationen zur Entwicklung von Teams-Apps finden Sie in der <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Dokumentation für Teams-Entwickler.</a>

![Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung](media/upload-custom-apps.png)

## <a name="develop"></a>Entwickeln

### <a name="create-your-app"></a>Erstellen ihrer App

Die Microsoft Teams-Entwicklerplattform erleichtert Entwicklern die Integration Ihrer eigenen Apps und Dienste, um die Produktivität zu steigern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu fördern. Auf der Plattform von Teams integrierte Apps sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows, die sie direkt in den Kontext Ihrer Zusammenarbeitsplattform integrieren. Weitere Informationen finden Sie in der Dokumentation für <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams-Entwickler.</a>

## <a name="validate"></a>Überprüfen

### <a name="get-the-app-package"></a>Herunterladen des App-Pakets

Wenn die App für die Produktion bereit ist, sollte der Entwickler ein App-Paket erstellen. Dazu können sie <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> verwenden. Diese senden Ihnen die Datei im ZIP-Format.

Microsoft verwendet <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">diese Richtlinien,</a> um sicherzustellen, dass Apps den Qualitäts- und Sicherheitsstandards des globalen Teams-Apps-Store entsprechen.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Zulassen, dass vertrauenswürdige Benutzer benutzerdefinierte Apps hochladen

Um zu überprüfen, ob die App in Ihrem Produktions mandant ordnungsgemäß funktioniert, müssen Sie es sich selbst und/oder vertrauenswürdigen Benutzern gestatten, benutzerdefinierte Apps in den Produktions mandanten hochzuladen. Zu diesem Grund <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">verwenden Sie Richtlinien für die</a> App-Einrichtung.

> [!NOTE]
> Wenn Sie unsicher sind, die App zur Überprüfung in Ihren Produktions mandanten hochzuladen, können Sie diesen [](#upload) Schritt [](#set-up-and-manage) überspringen und die Schritte in den Abschnitten "Hochladen" und "Einrichten und Verwalten" ausführen, um die nichtvalidierte App im App Store Ihrer Organisation zu veröffentlichen. Schränken Sie dann den Zugriff auf diese App auf sich selbst und Benutzer ein, deren vertrauenswürdige Benutzer Sie sind. Diese Benutzer können die App dann aus dem App Store Ihrer Organisation herunterladen, um die Überprüfung durchzuführen. Verwenden Sie nach der Überprüfung der App dieselben Berechtigungsrichtlinien, um den Zugriff zu öffnen und die App für die Produktionsnutzung zu verwenden.

Führen Sie die folgenden Schritte aus, um vertrauenswürdigen Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen:

1. Aktivieren Sie die **Organisationsweite Einstellung "Interaktion mit** benutzerdefinierten Apps zulassen". Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps** verwalten", und klicken Sie dann auf  >   **"Organisationsweite App-Einstellungen".**
    2. Aktivieren **Sie unter "Benutzerdefinierte Apps"** die Schaltfläche "Interaktion mit benutzerdefinierten **Apps zulassen",** und klicken Sie dann auf **"Speichern".**
2. Deaktivieren Sie die Einstellung **"Benutzerdefinierte Apps hochladen"** in der globalen App-Setuprichtlinie. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den Setuprichtlinien für Teams-Apps, und klicken Sie dann auf die globale  >   **Richtlinie (organisationsweite** Standardrichtlinie).
    2. Deaktivieren Sie **"Benutzerdefinierte Apps hochladen",** und klicken Sie dann auf **"Speichern".**
3. Erstellen Sie eine neue App-Setuprichtlinie, die das Hochladen benutzerdefinierter Apps und das Zuweisen dieser Richtlinie zu Ihrer Gruppe von vertrauenswürdigen Benutzern ermöglicht. Gehen Sie dazu so vor:
    1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den Setuprichtlinien für Teams-Apps, und klicken Sie dann auf  >   **"Hinzufügen".** Geben Sie der neuen Richtlinie einen Namen und eine Beschreibung, aktivieren Sie **"Benutzerdefinierte Apps hochladen",** und klicken Sie dann auf **"Speichern".**
    2. Wählen Sie die neue Richtlinie aus, die Sie erstellt haben, und klicken Sie dann **auf "Benutzer verwalten".** Suchen Sie nach einem Benutzer, klicken **Sie auf**"Hinzufügen" und dann auf **"Übernehmen".** Wiederholen Sie diesen Schritt, um die Richtlinie allen vertrauenswürdigen Benutzern zuzuordnen.

        ![Screenshot der Seite "App-Setuprichtlinie hinzufügen"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Diese Benutzer können jetzt das App-Manifest hochladen, um zu überprüfen, ob die App im Produktions mandant ordnungsgemäß funktioniert.

## <a name="upload"></a>Hochladen

Laden Sie die App hoch, um die App Benutzern im App Store Ihrer Organisation zur Verfügung zu stellen. Dies können Sie auf der Seite <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">"Apps</a> verwalten" im Microsoft Teams Admin Center tun.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**
2. Klicken **Sie auf "Hochladen",** **dann auf**"Datei auswählen" und dann auf das App-Paket, das Sie vom Entwickler erhalten haben.

   ![Screenshot des Hochladens einer App im Admin Center](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Einrichten und Verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die App

Standardmäßig können alle Benutzer in Ihrer Organisation im App Store Ihrer Organisation auf die App zugreifen. Um einzuschränken und zu steuern, wer über die Berechtigung zur Verwendung der App verfügt, können Sie eine Berechtigungsrichtlinie für die App erstellen und zuweisen. Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der App, die Benutzer entdecken können

Standardmäßig müssen Benutzer die App finden, die sie haben, zum App Store Ihrer Organisation wechseln und nach der App suchen. Um Benutzern den Zugriff auf die App zu ermöglichen, können Sie die App an die App-Leiste in Teams anheften. Erstellen Sie dazu eine App-Setuprichtlinie, und weisen Sie sie Benutzern zu. Weitere Informationen finden Sie unter "Verwalten von <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Richtlinien für das Einrichten von Apps in Teams".</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>Durchsuchen des Überwachungsprotokolls nach Ereignissen der Teams-App

Sie können das Überwachungsprotokoll durchsuchen, um die Aktivitäten von Teams-Apps in Ihrer Organisation anzeigen. Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Sehen einer Liste der im Überwachungsprotokoll protokollierten Teams-Aktivitäten finden Sie unter Durchsuchen des Überwachungsprotokolls nach Ereignissen <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">in Teams.</a>

Bevor Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst die Überwachung im <a href="https://protection.office.com" target="_blank">Security & Compliance Center aktivieren.</a> Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">der Überwachungsprotokollsuche.</a> Beachten Sie, dass Überwachungsdaten nur ab dem Punkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="discover-and-adopt"></a>Entdecken und Übernehmen

Benutzer mit Berechtigungen für die App finden sie im App Store Ihrer Organisation. Wechseln Sie **auf der Seite *"Apps"*** zu "Für Ihre Organisation erstellt", um die benutzerdefinierten Apps Ihrer Organisation zu finden.

![Screenshot der Seite "Apps" mit veröffentlichter App ](media/custom-app-lifecycle-discovery.png)

Wenn Sie eine Setuprichtlinie für Apps erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um den Benutzern, denen die Richtlinie zugewiesen wurde, einfachen Zugriff zu ermöglichen.

## <a name="update"></a>Aktualisieren

Um eine App zu aktualisieren, sollten Entwickler weiterhin die Schritte in den Abschnitten ["Entwickeln"](#develop) und ["Überprüfen"](#validate) ausführen.

Sie können die App auf der Seite "Apps verwalten" im Microsoft Teams Admin Center aktualisieren. Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".** Klicken Sie auf den Namen der App, und klicken Sie dann auf **"Aktualisieren".** Dadurch wird die vorhandene App ersetzt, und alle Berechtigungsrichtlinien und Richtlinien zum Einrichten von Apps bleiben für die aktualisierte App erhalten.

### <a name="end-user-update-experience"></a>Updateerfahrung für Endbenutzer

In den meisten Fällen wird nach Abschluss eines Updates der App die neue Version automatisch für Endbenutzer angezeigt. Es gibt jedoch einige Updates für das <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams-Manifest,</a> für die die Benutzerakzeptanz erforderlich ist, um den Vorgang abschließen zu können:

* Ein Bot wurde hinzugefügt oder entfernt
* Die "botId"-Eigenschaft eines vorhandenen Bots wurde geändert
* Die Eigenschaft "isNotificationOnly" eines vorhandenen Bots wurde geändert
* Die Eigenschaft "supportsFiles" des Bots wurde geändert.
* Eine Nachrichtenerweiterung wurde hinzugefügt oder entfernt
* Ein neuer Connector wurde hinzugefügt
* Eine neue statische Registerkarte wurde hinzugefügt
* Eine neue konfigurierbare Registerkarte wurde hinzugefügt
* Eigenschaften in "webApplicationInfo" geändert

![Screenshot der Liste "Apps" mit Apps, für die eine neue Version verfügbar ist](media/manage-your-custom-apps-update1.png)

![Screenshot der Upgradeoption für eine App](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Verwandte Themen

- [Veröffentlichen einer benutzerdefinierten App, die über die Übermittlungs-API für Teams-Apps übermittelt wird](submit-approve-custom-apps.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
