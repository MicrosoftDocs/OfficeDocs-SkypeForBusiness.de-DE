---
title: Verwenden Sie die Teams-App-Übermittlungs-API, um Ihre benutzerdefinierten Apps zu übermitteln und zu genehmigen
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
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
ms.openlocfilehash: 644e4afd28dbec27385516ce3e0676eb9ea27ef1
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837525"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Veröffentlichen einer benutzerdefinierten App, die mithilfe der Teams-App-Übermittlungs-API übermittelt wurde

Dieser Artikel bietet eine durchgängige Anleitung, wie Sie Ihre Teams-Anwendung von der Entwicklung über die Bereitstellung bis zur Ermittlung bringen. Sie erhalten einen Überblick über die verbundenen Erfahrungen, die Teams über den App-Lebenszyklus hinweg bereitstellt, um die Entwicklung, Bereitstellung und Verwaltung benutzerdefinierter Apps im App Store Ihrer Organisation zu optimieren.

Wir behandeln jeden Schritt des Lebenszyklus, einschließlich der Art und Weise, wie Entwickler die Teams-App-Übermittlungs-API verwenden können, um benutzerdefinierte Apps direkt an das Microsoft Teams Admin Center zu übermitteln, damit Sie diese überprüfen und genehmigen können, wie Sie Richtlinien zum Verwalten von Apps für Benutzer in Ihrer Organisation festlegen und wie Ihre Benutzer sie in Teams entdecken.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung.":::

Dieser Leitfaden konzentriert sich auf die Teams-Aspekte der App und richtet sich an Administratoren und IT-Experten. Informationen zum Entwickeln von Teams-Apps finden Sie in der [Teams-Entwicklerdokumentation](/microsoftteams/platform).

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art, die Sie verwenden, hängt davon ab, wie Sie die App abrufen. Dieser Artikel konzentriert sich auf das Genehmigen und Veröffentlichen einer benutzerdefinierten App, die ein Entwickler über die Teams-App-Übermittlungs-API übermittelt. Die andere Methode, das Hochladen einer benutzerdefinierten App, wird verwendet, wenn ein Entwickler Ihnen ein App-Paket im ZIP-Format sendet. Weitere Informationen zu dieser Methode finden Sie unter [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](/microsoftteams/upload-custom-apps). Das App-Genehmigungs-Widget ist in GCC-Mandanten nicht verfügbar.

> [!IMPORTANT]
> Diese Methode ist in GCC-Umgebungen nicht verfügbar. [Hochladen einer benutzerdefinierten App](upload-custom-apps.md), um sie in GCC-Umgebungen zu veröffentlichen.

## <a name="develop"></a>Entwickeln

### <a name="create-the-app"></a>Erstellen der App

Die Microsoft Teams-Entwicklerplattform macht es Entwicklern leicht, Ihre eigenen Apps und Dienste zu integrieren, um die Produktivität zu verbessern, Entscheidungen schneller zu treffen und die Zusammenarbeit mit bestehenden Inhalten und Workflows zu fördern. Auf der Teams-Plattform erstellte Apps sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows, die sie direkt in den Kontext Ihrer Plattform für die Zusammenarbeit bringen. Weitere Informationen finden Sie in der [Teams-Entwicklerdokumentation](/microsoftteams/platform).

### <a name="submit-the-app"></a>Übermitteln der App

Wenn die App für die Verwendung in der Produktion bereit ist, kann der Entwickler die App mithilfe der Teams-App-Übermittlungs-API übermitteln, die von [Graph-API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), einer integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) wie Visual Studio Code oder einer Plattform wie Power Apps und Power Virtual Agents aufgerufen werden kann. Dadurch wird die App auf der Seite [Apps verwalten](/microsoftteams/manage-apps) des Teams Admin Center verfügbar, wo Sie sie überprüfen und genehmigen können.

Die Teams-App-Übermittlungs-API, die [auf Microsoft Graph basiert](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), ermöglicht Ihrer Organisation die Entwicklung auf der Plattform Ihrer Wahl und automatisiert den Prozess der Einreichung bis zur Genehmigung für benutzerdefinierte Apps in Teams.

Hier ist ein Beispiel dafür, wie dieser App-Übermittlungsschritt in Visual Studio Code aussieht:

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Screenshot der App-Übermittlung in Visual Studio Code.":::

Beachten Sie, dass die App dadurch noch nicht im App Store Ihrer Organisation veröffentlicht wird. Dieser Schritt übermittelt die App an das Teams Admin Center, wo Sie sie für die Veröffentlichung im App Store Ihrer Organisation genehmigen können.

Weitere Informationen zur Verwendung der Graph-API zum Übermitteln von Apps finden Sie [hier](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Benachrichtigen

Sie können Benachrichtigungen aktivieren, damit Sie wissen, wann Entwickler eine neue Anwendung zur Überprüfung und Genehmigung übermitteln. Sie erhalten auch Benachrichtigungen, wenn Entwickler App-Updates übermitteln. Um App-Übermittlungsbenachrichtigungen im Teams Admin Center zu aktivieren, wechseln Sie zu **Benachrichtigungen und Warnungen** > **[Regeln](https://admin.teams.microsoft.com/notifications/rules)** > **App-Übermittlungen**, und aktivieren Sie die Regel, indem Sie den Status zu **Aktiv** ändern. Diese Einstellung ist standardmäßig deaktiviert. Sie müssen ein globaler Administrator oder Teams-Administrator sein, um diese Einstellung zu aktivieren.

Nachdem Sie diese Einstellung aktiviert haben, erhalten Sie Benachrichtigungen im **Team Admin Benachrichtigungen und Benachrichtigungen** unter einem neuen Kanal namens **App-Übermittlungen**. Alternativ können Sie ein vorhandenes Team und einen vorhandenen Kanal auswählen, um Benachrichtigungen an ein bestimmtes Team und einen bestimmten Kanal zu senden. Führen Sie hierzu folgende Schritte aus:

1. Aktivieren Sie in der **App-Übermittlungsregel** das Kontrollkästchen **Kanalbenachrichtigung** unter **Aktionen**.
1. Wählen Sie die Schaltfläche **Kanal auswählen** aus.
1. Suchen Sie nach einem hinzuzufügenden Team.
1. Suchen Sie nach einem hinzuzufügenden Kanal.
1. Wählen Sie **Anwenden** aus.

   :::image type="content" source="media/channel-alert.png" alt-text="Kontrollkästchen für benutzerdefinierte Kanalbenachrichtigungen." lightbox="media/channel-alert.png":::

> [!NOTE]
> Aktivieren Sie das Kontrollkästchen **Standardkanalwarnung**, um Benachrichtigungen an das Team für **Administrationswarnungen und -benachrichtigungen** im Kanal für **App-Übermittlungen** zu erhalten.

:::image type="content" source="media/default-channel-alert.png" alt-text="Standardbenachrichtigungskontrollkästchen für Kanalbenachrichtigungen." lightbox="media/default-channel-alert.png":::

Sie können auch Benachrichtigungen für einen externen Webhook einrichten, indem Sie eine öffentliche Webhook-URL angeben, nachdem Sie das **Webhook-Kontrollkästchen** aktiviert haben. Eine JSON-Benachrichtigungsnutzlast wird an Ihre Webhook-URL gesendet.

:::image type="content" source="media/app-submission-notification.png" alt-text="App-Übermittlungsbenachrichtigung." lightbox="media/app-submission-notification.png":::

Nachdem Sie die App-Übermittlungsregel eingerichtet haben, können Sie Benachrichtigungskarten im angegebenen Kanal überprüfen, um App-Details anzuzeigen, und **Details anzeigen** auswählen, um Apps im Teams Admin Center zu öffnen.

## <a name="validate"></a>Validieren

Die Seite [Apps verwalten](/microsoftteams/manage-apps) im Teams Admin Center (gehen Sie in der linken Navigation zu [**Teams-Apps** > **Apps verwalten**](https://admin.teams.microsoft.com/manage-apps)) gibt Ihnen einen Einblick in alle Teams-Apps für Ihre Organisation. Das Widget **Ausstehende Genehmigung** oben auf der Seite informiert Sie, wenn eine benutzerdefinierte Anwendung zur Genehmigung vorgelegt wird.

In der Tabelle zeigt eine neu eingereichte App automatisch den **Veröffentlichungsstatus** **Übermittelt** und den **Status** **Blockiert** an. Sie können die **Veröffentlichungsstatusspalte** in absteigender Reihenfolge sortieren, um die App schnell zu finden.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="Veröffentlichungsstatus." lightbox="media/custom-app-lifecycle-validate-app.png":::

Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln. Auf der Registerkarte **Info** können Sie Details zur App anzeigen, einschließlich Beschreibung, Status, Absender und App-ID.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="„App-Details“-Seite für eine übermittelte App" lightbox="media/custom-app-lifecycle-app-details.png":::

Weitere Informationen zur Verwendung der Graph-API zur Überprüfung des **Veröffentlichungsstatus** finden Sie [hier](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Veröffentlichen

Wenn Sie bereit sind, die App Benutzern zur Verfügung zu stellen, veröffentlichen Sie die App.

1. Melden Sie sich beim Teams Admin Center an, und wechseln Sie zu **Teams-App** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Wählen Sie den App-Namen aus, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann im Feld **Veröffentlichungsstatus** die Option **Veröffentlichen** aus.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="Schaltfläche &quot;Veröffentlichen&quot; auf der App-Detailseite.":::

Nachdem Sie die App veröffentlicht haben, ändert sich der **Veröffentlichungsstatus** in **Veröffentlicht** und der **Status** in **Zugelassen**.

## <a name="set-up-and-manage"></a>Einrichten und Verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die App

Standardmäßig können alle Benutzer in Ihrer Organisation auf die App im App Store Ihrer Organisation zugreifen. Um einzuschränken und zu steuern, wer über die Berechtigung zur Verwendung der App verfügt, können Sie eine App-Berechtigungsrichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der App zum Ermitteln für Benutzer

Standardmäßig müssen Benutzer, um die App zu finden, den App-Store Ihres Unternehmens aufrufen und dort nach ihr suchen oder suchen lassen. Um Benutzern den Zugriff auf die App zu erleichtern, können Sie die App an die App-Leiste in Teams anheften. Erstellen Sie hierzu eine App-Setuprichtlinie, und weisen Sie sie Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Durchsuchen der Audit-Protokolle nach App-Ereignissen in Teams

Sie können das Überwachungsprotokoll durchsuchen, um die Teams-Apps-Aktivität in Ihrer Organisation anzuzeigen. Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Anzeigen einer Liste der im Überwachungsprotokoll protokollierten Teams-Aktivitäten finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Teams](audit-log-events.md).

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im [Security & Compliance Center](https://sip.protection.office.com/) die Überwachung aktivieren. Weitere Informationen finden Sie unter [Die Überwachungsprotokollsuche ein- oder ausschalten](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="discover-and-adopt"></a>Entdecken und übernehmen

Benutzer, die über Berechtigungen für die App verfügen, können sie im App Store Ihrer Organisation finden. Wechseln Sie auf der Seite Apps zu **Erstellt für *Ihren Organisationsnamen***, um die benutzerdefinierten Apps Ihrer Organisation zu finden.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Apps-Seite mit veröffentlichter App." lightbox="media/custom-app-lifecycle-discovery.png":::

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, damit die Benutzer, denen die Richtlinie zugewiesen wurde, leicht darauf zugreifen können.

## <a name="update"></a>Aktualisieren

Um eine App zu aktualisieren, sollten Entwickler weiterhin die Schritte im Abschnitt [Entwickeln](#develop) ausführen.

Wenn der Entwickler ein Update an eine veröffentlichte benutzerdefinierte App übermittelt, werden Sie im Widget **Ausstehende Genehmigung** der Seite [Apps verwalten](/microsoftteams/manage-apps) benachrichtigt. In der Tabelle wird der **Veröffentlichungsstatus** der App auf **Übermittelt aktualisieren** festgelegt. Sie werden auch im **Team Admin Benachrichtigungen und Benachrichtigungen** unter dem **App-Übermittlungskanal** benachrichtigt, wenn Sie Benachrichtigungen zur App-Übermittlung aktiviert haben. Die Benachrichtigungskarte enthält einen Link, über den Sie direkt zur App im Teams Admin Center gelangen. Weitere Informationen zum Aktivieren von App-Übermittlungsbenachrichtigungen finden Sie unter [Benachrichtigen](#notify).

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="Seite „Apps verwalten“ mit ausstehenden Anfragen und App-Status." lightbox="media/custom-app-lifecycle-update-submitted.png":::

So prüfen und veröffentlichen Sie ein App-Update:

1. Wechseln Sie in der linken Navigation des Teams Admin Center zu **Teams-Apps** > **Apps verwalten**.
1. Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann **Update verfügbar** aus, um Details zum Update anzuzeigen.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="Seite &quot;App-Details&quot;." lightbox="media/custom-app-lifecycle-update-app.png":::

1. Wenn Sie fertig sind, wählen Sie **Veröffentlichen** aus, um das Update zu veröffentlichen. Dadurch wird die vorhandene App ersetzt, die Versionsnummer aktualisiert und der **Veröffentlichungsstatus** in **Veröffentlicht** geändert. Alle App-Berechtigungsrichtlinien und App-Setup-Richtlinien bleiben für die aktualisierte App erzwungen.

    Wenn Sie das Update ablehnen, bleibt die frühere Version der App veröffentlicht.

Beachten Sie Folgendes:

* Wenn eine App genehmigt wird, kann jeder ein Update für die App einreichen. Dies bedeutet, dass andere Entwickler, einschließlich des Entwicklers, der die App ursprünglich eingereicht hat, ein Update für die App einreichen können.
* Wenn ein Entwickler eine App einreicht und die Anfrage aussteht, kann nur derselbe Entwickler ein Update für die App einreichen. Andere Entwickler können ein Update erst einreichen, nachdem die App genehmigt wurde.

Weitere Informationen zur Verwendung der Graph-API zum Aktualisieren von Apps finden Sie [hier](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-articles"></a>Verwandte Artikel

* [Eine benutzerdefinierte App veröffentlichen, indem Sie ein App-Paket hochladen](upload-custom-apps.md)
* [Verwalten Sie Ihre Apps im Microsoft Teams Admin Center](manage-apps.md)
* [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
* [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
* [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
* [Teams-Überwachung und -Warnung](alerts/teams-admin-alerts.md)
* [Microsoft Graph API für Teams-Apps](alerts/teams-admin-alerts.md)
