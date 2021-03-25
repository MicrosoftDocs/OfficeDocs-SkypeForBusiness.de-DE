---
title: Verwenden der Teams App Submission API zum Übermitteln und Genehmigen Ihrer benutzerdefinierten Apps
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
description: Erfahren Sie, wie Sie Ihre benutzerdefinierten Apps genehmigen, die mit der Teams App Submission API in Microsoft Teams übermittelt werden.
ms.openlocfilehash: 8c12d93a0b4420fd248064c69308e8049dc6326f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116973"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Veröffentlichen einer benutzerdefinierten App, die über die Übermittlungs-API für Teams-Apps übermittelt wird

## <a name="overview"></a>Übersicht

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Verwendung hängt davon ab, wie Sie die App erhalten. Dieser Artikel befasst sich mit dem Genehmigen und Veröffentlichen einer benutzerdefinierten App, die ein Entwickler über die **Übermittlungs-API für Teams-Apps übermittelt.** Die andere Methode, das Hochladen einer benutzerdefinierten App, wird verwendet, wenn Ein Entwickler Ihnen ein App-Paket im ZIP-Format sendet. Weitere Informationen zu dieser Methode finden Sie unter <a href="/microsoftteams/upload-custom-apps" target="_blank">Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets.</a> Das Widget "App genehmigen" steht in GCC-Mandanten nicht zur Verfügung. 

> [!IMPORTANT]
> Diese Methode ist derzeit für GCC-Umgebungen nicht verfügbar. Sie müssen das Hochladen *einer benutzerdefinierten App-Methode* verwenden.

Dieser Artikel enthält eine end-to-end-Anleitung, wie Sie Ihre Teams-App von der Entwicklung über die Bereitstellung bis zur Discovery verwenden. Sie erhalten einen Überblick über die verbundenen Benutzererfahrungen, die Teams über den gesamten App-Lebenszyklus hinweg bietet, um die Entwicklung, Bereitstellung und Verwaltung benutzerdefinierter Apps im App Store Ihrer Organisation zu optimieren.

Wir gehen auf jeden Schritt des Lebenszyklus ein, einschließlich der Art und Weise, wie Entwickler die Übermittlungs-API für Teams-Apps verwenden können, um benutzerdefinierte Apps direkt an das Microsoft Teams Admin Center zu übermitteln, damit Sie sie überprüfen und genehmigen können, wie Richtlinien zum Verwalten von Apps für Benutzer in Ihrer Organisation festgelegt werden und wie Ihre Benutzer sie in Teams entdecken.

![Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung](media/custom-app-lifecycle.png)

Dieser Leitfaden konzentriert sich auf die Teams-Aspekte der App und richtet sich an Administratoren und IT-Profis. Informationen zum Entwickeln von Teams-Apps finden Sie in der <a href="/microsoftteams/platform" target="_blank">Dokumentation zu Teams-Entwicklern.</a>

## <a name="develop"></a>Entwickeln

### <a name="create-the-app"></a>Erstellen der App

Die Microsoft Teams-Entwicklerplattform erleichtert Entwicklern die Integration Eigener Apps und Dienste, um die Produktivität zu verbessern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu fördern. Apps, die auf der Teams-Plattform erstellt wurden, sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows und bringen sie direkt in den Kontext Ihrer Zusammenarbeitsplattform. Weitere Informationen finden Sie in der <a href="/microsoftteams/platform" target="_blank">Dokumentation zu Teams-Entwicklern.</a>

### <a name="submit-the-app"></a>Übermitteln der App

Wenn die App für die Produktion einsatzbereit ist, kann der Entwickler die App mithilfe der Teams-App-Übermittlungs-API übermitteln, die über die <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph-API,</a>eine integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) wie Visual Studio Code oder eine Plattform wie Power Apps und Power Virtual Agents aufgerufen werden kann. Dadurch steht die App <a href="/microsoftteams/manage-apps" target="_blank"></a> auf der Seite "Apps verwalten" im Microsoft Teams Admin Center zur Verfügung, auf der Sie, der Administrator, sie überprüfen und genehmigen können.this

Die auf Microsoft <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Graph</a>aufgebaute Übermittlungs-API für Teams-Apps ermöglicht Ihrer Organisation die Entwicklung auf der Plattform Ihrer Wahl und automatisiert den Übermittlungs- und Genehmigungsprozess für benutzerdefinierte Apps in Teams.

Hier sehen Sie ein Beispiel dafür, wie dieser Schritt für die App-Übermittlung in Visual Studio aussieht:

![Übermitteln einer App in Visual Studio Code](media/custom-app-lifecycle-submit-app.png)

Beachten Sie, dass die App dadurch noch nicht im App Store Ihrer Organisation veröffentlicht wird. In diesem Schritt wird die App an das Microsoft Teams Admin Center übermittelt, wo Sie sie für die Veröffentlichung im App Store Ihrer Organisation genehmigen können.

Weitere Informationen zur Verwendung der Graph-API zum Übermitteln von Apps finden Sie <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">hier.</a>

## <a name="validate"></a>Überprüfen

Auf <a href="/microsoftteams/manage-apps" target="_blank">der</a> Seite "Apps verwalten" im Microsoft Teams Admin Center (im linken Navigationsbereich zu **Teams-Apps** Apps verwalten, können Sie Apps verwalten) eine Ansicht aller  >  Teams-Apps für Ihre Organisation anzeigen. Das **Widget "Ausstehende Genehmigung"** oben auf der Seite informiert Sie, wann eine benutzerdefinierte App zur Genehmigung übermittelt wird.

In der Tabelle zeigt eine neu übermittelte App automatisch den Veröffentlichungsstatus **Übermittelt** **und** **den Status** blockiert **an.** Sie können die Spalte **Veröffentlichungsstatus** in absteigender Reihenfolge sortieren, um die App schnell zu finden.

![Veröffentlichungsstatus ](media/custom-app-lifecycle-validate-app.png)

Klicken Sie auf den Namen der App, um zur Seite mit den App-Details zu wechseln. Auf der **Registerkarte Informationen** können Sie Details zur App anzeigen, einschließlich Beschreibung, Status, Absender und App-ID.

![Seite "App-Details" für eine übermittelte App](media/custom-app-lifecycle-app-details.png)

Weitere Informationen zur Verwendung der Graph-API zum Überprüfen des **Veröffentlichungsstatus** finden Sie <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">hier.</a>

## <a name="publish"></a>Veröffentlichen

Wenn Sie bereit sind, die App benutzern zur Verfügung zu stellen, veröffentlichen Sie die App.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken Sie auf den App-Namen, um zur  Seite mit den App-Details zu wechseln, und wählen Sie dann im Feld Veröffentlichungsstatus die Option **Veröffentlichen aus.**

    Nachdem Sie die App veröffentlicht haben, ändert sich der **Veröffentlichungsstatus** in **Veröffentlicht,** und der **Status** wird automatisch in **Zulässig geändert.**

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

![Seite "Apps" mit veröffentlichter App ](media/custom-app-lifecycle-discovery.png)

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um den Benutzern, denen die Richtlinie zugewiesen wurde, einfachen Zugriff zu ermöglichen.

## <a name="update"></a>Aktualisieren

Zum Aktualisieren einer App sollten Entwickler weiterhin die Schritte im Abschnitt [Entwickeln](#develop) ausführen.

Wenn der Entwickler ein Update an eine veröffentlichte benutzerdefinierte App übermittelt, werden Sie im **Widget Für** die Genehmigung ausstehend auf der Seite <a href="/microsoftteams/manage-apps" target="_blank">Apps verwalten</a> benachrichtigt. In der Tabelle wird der **Veröffentlichungsstatus** der App auf **Übermittelt aktualisieren festgelegt.**

![Seite "Apps verwalten" mit ausstehenden Anforderungen und dem App-Status ](media/custom-app-lifecycle-update-submitted.png)

So überprüfen und veröffentlichen Sie ein App-Update:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie **dann Update verfügbar** aus, um details des Updates zu überprüfen.

    ![Seite "App-Details"](media/custom-app-lifecycle-update-app.png)
3. Wenn Sie fertig sind, wählen Sie **Veröffentlichen aus,** um das Update zu veröffentlichen. Dadurch wird die vorhandene App ersetzt, die Versionsnummer aktualisiert und der **Veröffentlichungsstatus** in Veröffentlicht **geändert.** Alle Richtlinien für Die App-Berechtigung und Die App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

    Wenn Sie das Update ablehnen, bleibt die frühere Version der App veröffentlicht.

Beachten Sie Folgendes:

- Wenn eine App genehmigt wird, kann jeder ein Update an die App übermitteln. Dies bedeutet, dass andere Entwickler, einschließlich des Entwicklers, der die App ursprünglich übermittelt hat, ein Update an die App übermitteln können.
- Wenn ein Entwickler eine App übermittelt und die Anforderung aussteht, kann nur derselbe Entwickler ein Update an die App übermitteln. Andere Entwickler können ein Update erst übermitteln, nachdem die App genehmigt wurde.

Weitere Informationen zur Verwendung der Graph-API zum Aktualisieren von Apps finden Sie <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">hier.</a>

### <a name="update-experience-for-users"></a>Updateerfahrung für Benutzer

In den meisten Fällen wird die neue Version nach der Veröffentlichung eines App-Updates automatisch für Benutzer angezeigt. Es gibt jedoch einige Updates für das <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams-Manifest,</a> für die die Benutzerakzeptanz erforderlich ist:

* Ein Bot wurde hinzugefügt oder entfernt
* Die "botId"-Eigenschaft eines vorhandenen Bots wurde geändert
* Die Eigenschaft "isNotificationOnly" eines vorhandenen Bots wurde geändert
* Die Eigenschaft "supportsFiles" des Bots wurde geändert
* Eine Nachrichtenerweiterung wurde hinzugefügt oder entfernt
* Ein neuer Verbinder wurde hinzugefügt
* Eine neue statische Registerkarte wurde hinzugefügt
* Eine neue konfigurierbare Registerkarte wurde hinzugefügt
* Eigenschaften in "webApplicationInfo" geändert

![Neue Version verfügbar](media/manage-your-custom-apps-update1.png)

![Upgradeoption für eine App](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Verwandte Themen

- [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](upload-custom-apps.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
- <a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Microsoft Graph-API für Teams-Apps</a>