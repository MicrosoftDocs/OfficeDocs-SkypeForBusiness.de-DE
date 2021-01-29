---
title: Verwenden der Übermittlungs-API für Teams-Apps zum Übermitteln und Genehmigen Ihrer benutzerdefinierten Apps
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
description: Hier erfahren Sie, wie Sie Ihre benutzerdefinierten Apps genehmigen, die mit der Übermittlungs-API für Apps in Microsoft Teams übermittelt werden.
ms.openlocfilehash: 6b9304cf2af9e45dd9fd2955cda6498ce1dbc3ae
ms.sourcegitcommit: 6262deaede6f25b17624d7468eff7a2863eeacf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50043969"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Veröffentlichen einer benutzerdefinierten App, die über die Übermittlungs-API für Teams-Apps übermittelt wird

## <a name="overview"></a>Übersicht

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art und Weise, wie Sie sie verwenden, hängt davon ab, wie Sie die App erhalten. Dieser Artikel befasst sich mit dem Genehmigen und Veröffentlichen einer benutzerdefinierten App, die ein Entwickler über die **Übermittlungs-API für Teams-Apps übermittelt.** Die andere Methode, das Hochladen einer benutzerdefinierten App, wird verwendet, wenn Ihnen ein Entwickler ein App-Paket im ZIP-Format sendet. Weitere Informationen zu dieser Methode finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">"Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets".</a>

Dieser Artikel enthält eine End-to-End-Anleitung, wie Sie Ihre Teams-App von der Entwicklung über die Bereitstellung bis zur Ermittlung weiterverbauen können. Sie erhalten einen Überblick über die verbundenen Benutzererfahrungen, die Teams während des gesamten App-Lebenszyklus bietet, um das Entwickeln, Bereitstellen und Verwalten von benutzerdefinierten Apps im App Store Ihrer Organisation zu optimieren.

Wir gehen auf jeden Schritt des Lebenszyklus ein, einschließlich der Art und Weise, wie Entwickler die Übermittlungs-API für Teams-Apps verwenden können, um benutzerdefinierte Apps direkt an das Microsoft Teams Admin Center zu übermitteln, damit Sie diese überprüfen und genehmigen können, wie Richtlinien zum Verwalten von Apps für Benutzer in Ihrer Organisation festgelegt werden und wie ihre Benutzer sie in Teams entdecken.

![Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung](media/custom-app-lifecycle.png)

Dieser Leitfaden konzentriert sich auf die Aspekte von Teams der App und richtet sich an Administratoren und IT-Profis. Informationen zum Entwickeln von Teams-Apps finden Sie in der <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Dokumentation für Teams-Entwickler.</a>

## <a name="develop"></a>Entwickeln

### <a name="create-the-app"></a>Erstellen der App

Die Microsoft Teams-Entwicklerplattform erleichtert Entwicklern die Integration Ihrer eigenen Apps und Dienste, um die Produktivität zu steigern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu fördern. Auf der Plattform von Teams integrierte Apps sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows, die sie direkt in den Kontext Ihrer Zusammenarbeitsplattform integrieren. Weitere Informationen finden Sie in der Dokumentation für <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams-Entwickler.</a>

### <a name="submit-the-app"></a>Übermitteln der App

Wenn die App für die Produktion verwendet werden kann, kann der Entwickler die App mithilfe der Teams-App-Übermittlungs-API übermitteln, die von <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API,</a>einer integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) wie Visual Studio Code oder einer Plattform wie Power Apps und virtuellen Power Agents aufgerufen werden kann. Dadurch steht die App <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> auf der Seite "Apps verwalten" im Microsoft Teams Admin Center zur Verfügung, wo Sie als Administrator sie überprüfen und genehmigen können. Dies

Die auf Microsoft <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Graph</a>integrierte Übermittlungs-API für Teams-Apps ermöglicht Ihrer Organisation die Entwicklung auf der Plattform Ihrer Wahl und automatisiert den Übermittlungs-zu-Genehmigungsprozess für benutzerdefinierte Apps in Teams.

Im Folgenden finden Sie ein Beispiel dafür, wie dieser Schritt zur Übermittlung der App im Visual Studio aussieht:

![Übermitteln einer App im Visual Studio Code](media/custom-app-lifecycle-submit-app.png)

Beachten Sie, dass die App dadurch noch nicht im App Store Ihrer Organisation veröffentlicht wird. Mit diesem Schritt wird die App an das Microsoft Teams Admin Center übermittelt, wo Sie sie für die Veröffentlichung im App Store Ihrer Organisation genehmigen können.

Weitere Informationen zur Verwendung der Graph-API zum Übermitteln von Apps finden Sie <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">hier.</a>

## <a name="validate"></a>Überprüfen

Die <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Seite "Apps verwalten"</a> im Microsoft Teams Admin Center (in der linken Navigationsleiste unter **"Teams-Apps** verwalten", "Apps verwalten"), bietet Ihnen einen Einblick in alle  >  Teams-Apps für Ihre Organisation. Das **Widget "Ausstehende Genehmigung"** oben auf der Seite informiert Sie, wenn eine benutzerdefinierte App zur Genehmigung eingereicht wird.

In der Tabelle zeigt eine neu  übermittelte App automatisch den Veröffentlichungsstatus "Übermittelt" und den **Status** "Blockiert" **an.**  Sie können die Spalte **"Veröffentlichungsstatus"** in absteigender Reihenfolge sortieren, um die App schnell zu finden.

![Veröffentlichungsstatus ](media/custom-app-lifecycle-validate-app.png)

Klicken Sie auf den App-Namen, um zur Detailseite der App zu wechseln. Auf der **Registerkarte "Informationen"** können Sie Details zur App anzeigen, einschließlich Beschreibung, Status, Einreichung und App-ID.

![Seite "App-Details" für eine übermittelte App](media/custom-app-lifecycle-app-details.png)

Weitere Informationen zur Verwendung der Graph-API zum Überprüfen des **Veröffentlichungsstatus finden** Sie <a href="https://docs.microsoft.com/graph/api/appcatalogs-list-teamsapps?view=graph-rest-1.0&tabs=http#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">hier.</a>

## <a name="publish"></a>Veröffentlichen

Wenn Sie bereit sind, die App für Benutzer verfügbar zu machen, veröffentlichen Sie die App.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**
2. Klicken Sie auf den App-Namen, um zur  Detailseite der App zu wechseln, und wählen Sie dann im Feld "Veröffentlichungsstatus" die Option "Veröffentlichen" **aus.**

    Nachdem Sie die App veröffentlicht haben, ändert sich der **Veröffentlichungsstatus** **in** "Veröffentlicht", und der **Status** ändert sich automatisch in **"Zulässig".**

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

![Seite "Apps" mit veröffentlichter App ](media/custom-app-lifecycle-discovery.png)

Wenn Sie eine Setuprichtlinie für Apps erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um den Benutzern, denen die Richtlinie zugewiesen wurde, einfachen Zugriff zu ermöglichen.

## <a name="update"></a>Aktualisieren

Um eine App zu aktualisieren, sollten Entwickler die Schritte im Abschnitt ["Entwickeln" fortsetzen.](#develop)

Wenn der Entwickler ein Update an eine veröffentlichte benutzerdefinierte App  übermittelt, werden Sie im Widget "Ausstehende Genehmigung" der Seite "Apps <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">verwalten"</a> benachrichtigt. In der Tabelle wird der **Veröffentlichungsstatus** der App auf **"Update übermittelt" festgelegt.**

![Seite "Apps verwalten" mit ausstehenden Anforderungen und dem Status der App ](media/custom-app-lifecycle-update-submitted.png)

So überprüfen und veröffentlichen Sie ein App-Update:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**
2. Klicken Sie auf den App-Namen, um zur Detailseite der App zu wechseln, und wählen Sie dann **"Update verfügbar"** aus, um die Details des Updates zu überprüfen.

    ![Seite "App-Details"](media/custom-app-lifecycle-update-app.png)
3. Wenn Sie fertig sind, wählen Sie **"Veröffentlichen" aus,** um das Update zu veröffentlichen. Dadurch wird die vorhandene App ersetzt, die Versionsnummer aktualisiert und der **Veröffentlichungsstatus** in **"Veröffentlicht" geändert.** Alle Berechtigungsrichtlinien und Richtlinien für das Einrichten von Apps bleiben für die aktualisierte App erzwungen.

    Wenn Sie das Update ablehnen, bleibt die frühere Version der App veröffentlicht.

Beachten Sie Folgendes:

- Wenn eine App genehmigt wird, kann jeder Benutzer ein Update an die App übermitteln. Dies bedeutet, dass andere Entwickler, einschließlich des Entwicklers, der die App ursprünglich eingereicht hat, ein Update an die App übermitteln können.
- Wenn ein Entwickler eine App übermittelt und die Anforderung aussteht, kann nur derselbe Entwickler ein Update an die App übermitteln. Andere Entwickler können ein Update erst übermitteln, nachdem die App genehmigt wurde.

Weitere Informationen zur Verwendung der Graph-API zum Aktualisieren von Apps finden Sie <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">hier.</a>

### <a name="update-experience-for-users"></a>Updateerfahrung für Benutzer

In den meisten Fällen wird nach der Veröffentlichung eines App-Updates die neue Version automatisch für Benutzer angezeigt. Es gibt jedoch einige Updates für das <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams-Manifest,</a> für die die Benutzerakzeptanz erforderlich ist, um den Vorgang abschließen zu können:

* Ein Bot wurde hinzugefügt oder entfernt
* Die "botId"-Eigenschaft eines vorhandenen Bots wurde geändert
* Die Eigenschaft "isNotificationOnly" eines vorhandenen Bots wurde geändert
* Die Eigenschaft "supportsFiles" des Bots wurde geändert.
* Eine Nachrichtenerweiterung wurde hinzugefügt oder entfernt.
* Ein neuer Connector wurde hinzugefügt
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
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Microsoft Graph-API für Teams-Apps</a>
