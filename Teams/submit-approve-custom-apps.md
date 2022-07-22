---
title: Verwenden der Teams-App-Übermittlungs-API zum Übermitteln und Genehmigen Ihrer benutzerdefinierten Apps
author: guptaashish
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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre benutzerdefinierten Apps genehmigen, die mithilfe der Teams-App-Übermittlungs-API in Microsoft Teams übermittelt werden.
ms.openlocfilehash: 2fb0ab6778a0704b0cb60faef0d0fd739351ee10
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958070"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Veröffentlichen einer benutzerdefinierten App, die mithilfe der Teams-App-Übermittlungs-API übermittelt wurde

Dieser Artikel enthält end-to-end-Anleitungen, wie Sie Ihre Teams-App von der Entwicklung über die Bereitstellung bis hin zur Ermittlung nutzen können. Sie erhalten einen Überblick über die verbundenen Erfahrungen, die Teams über den gesamten App-Lebenszyklus hinweg bietet, um das Entwickeln, Bereitstellen und Verwalten von benutzerdefinierten Apps im App Store Ihrer Organisation zu optimieren.

Wir behandeln jeden Schritt des Lebenszyklus, einschließlich der Art und Weise, wie Entwickler die Teams-App-Übermittlungs-API verwenden können, um benutzerdefinierte Apps direkt an das Microsoft Teams Admin Center zu übermitteln, damit Sie diese überprüfen und genehmigen können, wie Sie Richtlinien zum Verwalten von Apps für Benutzer in Ihrer Organisation festlegen und wie Ihre Benutzer sie in Teams entdecken.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung.":::

Dieser Leitfaden konzentriert sich auf die Teams-Aspekte der App und richtet sich an Administratoren und IT-Experten. Informationen zum Entwickeln von Teams-Apps finden Sie in der [Teams-Entwicklerdokumentation](/microsoftteams/platform).

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art und Weise, wie Sie diese verwenden, hängt davon ab, wie Sie die App erhalten. Dieser Artikel befasst sich mit dem Genehmigen und Veröffentlichen einer benutzerdefinierten App, die ein Entwickler über die Teams-App-Übermittlungs-API übermittelt. Die andere Methode, das Hochladen einer benutzerdefinierten App, wird verwendet, wenn ein Entwickler Ihnen ein App-Paket im .zip Format sendet. Weitere Informationen zu dieser Methode finden Sie unter [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](/microsoftteams/upload-custom-apps). Das Widget für genehmigene Apps ist in GCC-Mandanten nicht verfügbar.

> [!IMPORTANT]
> Diese Methode ist derzeit für GCC-Umgebungen nicht verfügbar. Verwenden Sie in GCC das *Hochladen einer benutzerdefinierten App-Methode* .

## <a name="develop"></a>Entwickeln

### <a name="create-the-app"></a>Erstellen der App

Die Microsoft Teams-Entwicklerplattform macht es Entwicklern leicht, Ihre eigenen Apps und Dienste zu integrieren, um die Produktivität zu verbessern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu erstellen. Auf der Teams-Plattform erstellte Apps sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows, die sie direkt in den Kontext Ihrer Plattform für die Zusammenarbeit bringen. Weitere Informationen finden Sie in der [Teams-Entwicklerdokumentation](/microsoftteams/platform).

### <a name="submit-the-app"></a>Übermitteln der App

Wenn die App für die Verwendung in der Produktion bereit ist, kann der Entwickler die App mithilfe der Teams-App-Übermittlungs-API übermitteln, die von [Graph API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio Code oder einer Plattform wie Power Apps und Power Virtual Agents aufgerufen werden kann. Dadurch wird die App auf der Seite " [Apps verwalten"](/microsoftteams/manage-apps) im Teams Admin Center verfügbar gemacht, wo Sie sie überprüfen und genehmigen können.

Die teams-App-Übermittlungs-API, [die auf Microsoft Graph basiert](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), ermöglicht Es Ihrer Organisation, auf der Plattform Ihrer Wahl zu entwickeln, und automatisiert den Übermittlungs-zu-Genehmigungsprozess für benutzerdefinierte Apps in Teams.

Hier ist ein Beispiel dafür, wie dieser Schritt für die App-Übermittlung in Visual Studio Code aussieht:

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Übermitteln einer App in Visual Studio Code.":::

Beachten Sie, dass dadurch die App noch nicht im App Store Ihrer Organisation veröffentlicht wird. In diesem Schritt wird die App an das Teams Admin Center übermittelt, wo Sie sie für die Veröffentlichung im App Store Ihrer Organisation genehmigen können.

Weitere Informationen zur Verwendung der Graph API zum Übermitteln von Apps finden Sie [hier](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Benachrichtigen

Sie können Benachrichtigungen aktivieren, damit Sie wissen, wann Entwickler eine neue Anwendung zur Überprüfung und Genehmigung übermitteln. Sie erhalten auch Benachrichtigungen, wenn Entwickler App-Updates übermitteln. Um Benachrichtigungen zur App-Übermittlung im Teams Admin Center zu aktivieren, wechseln Sie zu **Benachrichtigungen & Benachrichtigungen** > **Regel-App-Übermittlungen****[](https://admin.teams.microsoft.com/notifications/rules)** > , und aktivieren Sie die Regel, indem Sie den Status in **"Aktiv**" ändern. Diese Einstellung ist standardmäßig deaktiviert. Sie müssen ein globaler Administrator oder Teams-Administrator sein, um diese Einstellung aktivieren zu können.

Nachdem Sie diese Einstellung aktiviert haben, erhalten Sie Benachrichtigungen im **Team Admin Benachrichtigungen und Benachrichtigungen** unter einem neuen Kanal namens **App-Übermittlungen**. Alternativ können Sie ein vorhandenes Team und einen vorhandenen Kanal auswählen, um Benachrichtigungen an ein bestimmtes Team und einen bestimmten Kanal zu senden. Führen Sie hierzu folgende Schritte aus:

1. Aktivieren Sie in der **App-Übermittlungsregel** das Kontrollkästchen **"Kanalbenachrichtigung** " unter **"Aktionen"**.
1. Wählen Sie die Schaltfläche " **Kanal auswählen" aus** .
1. Suchen Sie nach einem Team, das hinzugefügt werden soll.
1. Suchen Sie nach einem hinzuzufügenden Kanal.
1. Wählen Sie **"Übernehmen" aus**.

   :::image type="content" source="media/channel-alert.png" alt-text="Kontrollkästchen für benutzerdefinierte Kanalbenachrichtigungen." lightbox="media/channel-alert.png":::

> [!NOTE]
> Aktivieren Sie das Kontrollkästchen **"Standardkanalbenachrichtigung**", um Benachrichtigungen an das **Team Admin Benachrichtigungen und Benachrichtigungen** im **Kanal "App-Übermittlungen**" zu erhalten.

:::image type="content" source="media/default-channel-alert.png" alt-text="Standardbenachrichtigungskontrollkästchen für Kanalbenachrichtigungen." lightbox="media/default-channel-alert.png":::

Sie können auch Benachrichtigungen für einen externen Webhook einrichten, indem Sie eine öffentliche Webhook-URL angeben, nachdem Sie das **Webhook-Kontrollkästchen** aktiviert haben. Eine JSON-Benachrichtigungsnutzlast wird an Ihre Webhook-URL gesendet.

:::image type="content" source="media/app-submission-notification.png" alt-text="App-Übermittlungsbenachrichtigung." lightbox="media/app-submission-notification.png":::

Nachdem Sie die App-Übermittlungsregel eingerichtet haben, können Sie Benachrichtigungskarten im angegebenen Kanal überprüfen, um App-Details anzuzeigen, und **"Details anzeigen"** auswählen, um Apps im Teams Admin Center zu öffnen.

## <a name="validate"></a>Überprüfen

Auf der Seite ["Apps verwalten](/microsoftteams/manage-apps)" im Teams Admin Center (im linken Navigationsbereich wechseln Sie zu ["Apps verwalten" in **Teams-Apps** > ](https://admin.teams.microsoft.com/manage-apps)), erhalten Sie einen Einblick in alle Teams-Apps für Ihre Organisation. Das Widget " **Ausstehende Genehmigung** " am oberen Rand der Seite informiert Sie darüber, wann eine benutzerdefinierte App zur Genehmigung übermittelt wird.

In der Tabelle zeigt eine neu übermittelte App automatisch den **Veröffentlichungsstatus** " **Gesendet** " und den **Status** " **Blockiert**" an. Sie können die **Veröffentlichungsstatusspalte** in absteigender Reihenfolge sortieren, um die App schnell zu finden.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="Veröffentlichungsstatus." lightbox="media/custom-app-lifecycle-validate-app.png":::

Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln. Auf der Registerkarte " **Info** " können Sie Details zur App anzeigen, einschließlich Beschreibung, Status, Übermittlung und App-ID.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="Seite &quot;App-Details&quot; für eine übermittelte App." lightbox="media/custom-app-lifecycle-app-details.png":::

Weitere Informationen zur Verwendung des Graph API zum Überprüfen des **Veröffentlichungsstatus** finden Sie [hier](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Veröffentlichen

Wenn Sie bereit sind, die App für Benutzer verfügbar zu machen, veröffentlichen Sie die App.

1. Melden Sie sich beim Teams Admin Center an, und wechseln Sie zu **"Teams-Apps** > **[verwalten"](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Wählen Sie den App-Namen aus, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann im **Feld "Veröffentlichungsstatus** " die Option " **Veröffentlichen"** aus.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="Schaltfläche &quot;Veröffentlichen&quot; auf der App-Detailseite.":::

Nachdem Sie die App veröffentlicht haben, ändert sich der **Veröffentlichungsstatus** in **"Veröffentlicht** ", und der **Status** ändert sich in **"Zulässig**".

## <a name="set-up-and-manage"></a>Einrichten und Verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die App

Standardmäßig können alle Benutzer in Ihrer Organisation auf die App im App Store Ihrer Organisation zugreifen. Um einzuschränken und zu steuern, wer über die Berechtigung zur Verwendung der App verfügt, können Sie eine App-Berechtigungsrichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der app für Benutzer zu entdecken

Wenn Benutzer die App suchen möchten, müssen sie standardmäßig zum App Store Ihrer Organisation wechseln und danach suchen oder suchen. Um Benutzern den Zugriff auf die App zu erleichtern, können Sie die App an die App-Leiste in Teams anheften. Erstellen Sie dazu eine App-Setuprichtlinie, und weisen Sie sie Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Durchsuchen des Überwachungsprotokolls nach Teams-App-Ereignissen

Sie können das Überwachungsprotokoll durchsuchen, um die Aktivitäten von Teams-Apps in Ihrer Organisation anzuzeigen. Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Anzeigen einer Liste von Teams-Aktivitäten, die im Überwachungsprotokoll protokolliert werden, finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Teams](audit-log-events.md).

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im [Security & Compliance Center](https://sip.protection.office.com/) die Überwachung aktivieren. Weitere Informationen finden Sie unter [Die Überwachungsprotokollsuche ein- oder ausschalten](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="discover-and-adopt"></a>Entdecken und einführen

Benutzer, die über Berechtigungen für die App verfügen, können sie im App Store Ihrer Organisation finden. Wechseln Sie auf der Seite "Apps" zu ***"Für Ihre Organisation* erstellter Name**", um die benutzerdefinierten Apps Ihrer Organisation zu finden.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Seite &quot;Apps&quot; mit veröffentlichter App." lightbox="media/custom-app-lifecycle-discovery.png":::

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um für benutzer, denen die Richtlinie zugewiesen wurde, einfachen Zugriff zu erhalten.

## <a name="update"></a>Aktualisieren

Um eine App zu aktualisieren, sollten Entwickler weiterhin die Schritte im Abschnitt ["Entwickeln](#develop) " ausführen.

Wenn der Entwickler ein Update an eine veröffentlichte benutzerdefinierte App übermittelt, werden Sie im Widget " **Ausstehende Genehmigung"** der Seite ["Apps verwalten"](/microsoftteams/manage-apps) benachrichtigt. In der Tabelle wird der **Veröffentlichungsstatus** der App auf **"Übermittelt aktualisieren"** festgelegt. Sie werden auch im **Team Admin Benachrichtigungen und Benachrichtigungen** unter dem **App-Übermittlungskanal** benachrichtigt, wenn Sie Benachrichtigungen zur App-Übermittlung aktiviert haben. Die Benachrichtigungskarte enthält einen Link, über den Sie direkt zur App im Teams Admin Center gelangen. Weitere Informationen zum Aktivieren von App-Übermittlungsbenachrichtigungen finden Sie unter [Benachrichtigen](#notify).

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="Seite &quot;Apps verwalten&quot; mit ausstehenden Anforderungen und App-Status." lightbox="media/custom-app-lifecycle-update-submitted.png":::

So überprüfen und veröffentlichen Sie ein App-Update:

1. Wechseln Sie im linken Navigationsbereich des Teams Admin Centers zu **"Teams-Apps** > **verwalten"**.
1. Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann **"Update verfügbar"** aus, um details des Updates zu überprüfen.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="Seite &quot;App-Details&quot;." lightbox="media/custom-app-lifecycle-update-app.png":::

1. Wenn Sie fertig sind, wählen Sie **"Veröffentlichen** " aus, um das Update zu veröffentlichen. Dadurch wird die vorhandene App ersetzt, die Versionsnummer aktualisiert und der **Veröffentlichungsstatus** in **"Veröffentlicht**" geändert. Alle App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

    Wenn Sie das Update ablehnen, bleibt die frühere Version der App veröffentlicht.

Beachten Sie Folgendes:

* Wenn eine App genehmigt wird, kann jede Person ein Update an die App übermitteln. Dies bedeutet, dass andere Entwickler, einschließlich des Entwicklers, der die App ursprünglich übermittelt hat, ein Update an die App übermitteln können.
* Wenn ein Entwickler eine App übermittelt und die Anforderung aussteht, kann nur derselbe Entwickler ein Update an die App übermitteln. Andere Entwickler können ein Update erst übermitteln, nachdem die App genehmigt wurde.

Weitere Informationen zur Verwendung der Graph API zum Aktualisieren von Apps finden Sie [hier](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-articles"></a>Verwandte Artikel

* [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](upload-custom-apps.md)
* [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
* [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
* [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
* [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
* [Teams-Überwachung und -Warnung](alerts/teams-admin-alerts.md)
* [Microsoft Graph API für Teams-Apps](alerts/teams-admin-alerts.md)
