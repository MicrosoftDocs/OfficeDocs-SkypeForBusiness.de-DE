---
title: Verwenden der API Teams Zur Übermittlung von Apps zum Übermitteln und Genehmigen Ihrer benutzerdefinierten Apps
author: cichur
ms.author: v-mahoffman
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
description: Hier erfahren Sie, wie Sie Ihre benutzerdefinierten Apps genehmigen, die mit der API Teams Übermittlung von Apps im Microsoft Teams.
ms.openlocfilehash: ff115ab34c30bf2acfc7f24407045c1d44c4eade
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745511"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Veröffentlichen einer benutzerdefinierten App, die über die API Teams Übermittlung von Apps übermittelt wird

## <a name="overview"></a>Übersicht

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art der Verwendung hängt davon ab, wie Sie die App erhalten. Dieser Artikel befasst sich mit dem Genehmigen und Veröffentlichen einer benutzerdefinierten App, die ein Entwickler über die API für **Teams-Übermittlung übermittelt.** Die andere Methode, das Hochladen einer benutzerdefinierten App, wird verwendet, wenn Ihnen ein Entwickler ein App-Paket im Format .zip sendet. Weitere Informationen zu dieser Methode finden Sie unter <a href="/microsoftteams/upload-custom-apps" target="_blank">Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets.</a> Das Widget zum Genehmigen von Apps ist in GCC nicht verfügbar. 

> [!IMPORTANT]
> Diese Methode ist derzeit für andere GCC verfügbar. Sie müssen die Methode *zum Hochladen einer benutzerdefinierten App* verwenden.

Dieser Artikel enthält eine End-to-End-Anleitung, wie Sie Ihre Teams von der Entwicklung über die Bereitstellung bis zur Ermittlung weiterverhilfen können. Sie erhalten einen Überblick über die verbundenen Benutzererfahrungen, die von Teams während des gesamten App-Lebenszyklus bereitgestellt werden, um die Entwicklung, Bereitstellung und Verwaltung von benutzerdefinierten Apps im App Store Ihrer Organisation zu optimieren.

Wir gehen auf jeden Schritt des Lebenszyklus ein, einschließlich der Art und Weise, wie Entwickler die API für die Übermittlung von Teams-Apps verwenden können, um benutzerdefinierte Apps direkt an das Microsoft Teams Admin Center zu übermitteln, damit Sie diese überprüfen und genehmigen können, wie Richtlinien zum Verwalten von Apps für Benutzer in Ihrer Organisation festgelegt werden und wie Ihre Benutzer sie in Teams entdecken.

![Übersicht über ihre App von der Entwicklung bis zur Bereitstellung.](media/custom-app-lifecycle.png)

Dieser Leitfaden befasst sich Teams Aspekte der App und richtet sich an Administratoren und IT-Profis. Informationen zum Entwickeln von Teams-Apps finden Sie in der <a href="/microsoftteams/platform" target="_blank">Teams für Entwickler.</a>

## <a name="develop"></a>Entwickeln

### <a name="create-the-app"></a>Erstellen der App

Die Microsoft Teams-Entwicklerplattform erleichtert Entwicklern die Integration Ihrer eigenen Apps und Dienste, um die Produktivität zu steigern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu fördern. Apps, die auf der Teams-Plattform erstellt wurden, sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows und bringen sie direkt in den Kontext Ihrer Zusammenarbeitsplattform. Weitere Informationen finden Sie in der Dokumentation <a href="/microsoftteams/platform" target="_blank">Teams Entwickler .</a>

### <a name="submit-the-app"></a>Übermitteln der App

Wenn die App für die Produktion verwendet werden kann, kann der Entwickler die App mithilfe der API für die Teams-App-Übermittlung einreichen, die von [der Graph-API,](/graph/api/teamsapp-publish)einer integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) wie Visual Studio Code oder einer Plattform wie Power Apps und Power Virtual Agents aufgerufen werden kann. Dadurch steht die App <a href="/microsoftteams/manage-apps" target="_blank"></a> auf der Seite Apps verwalten im Microsoft Teams Admin Center zur Verfügung, auf der Sie, der Administrator, sie überprüfen und genehmigen können.dies

Die Teams-API für die Übermittlung von Apps, die auf <a href="/graph/api/teamsapp-publish" target="_blank">Microsoft Graph</a>aufgebaut ist, ermöglicht Es Ihrer Organisation, auf der Plattform Ihrer Wahl zu entwickeln und den Übermittlungs-zu-Genehmigungsprozess für benutzerdefinierte Apps auf ihrem Teams.

Im Folgenden finden Sie ein Beispiel dafür, wie dieser App-Einreichungsschritt in diesem Visual Studio Code:

![eine App im Visual Studio Code.](media/custom-app-lifecycle-submit-app.png)

Beachten Sie, dass die App dadurch noch nicht im App Store Ihrer Organisation veröffentlicht wird. Mit diesem Schritt wird die App an das Microsoft Teams Admin Center übermittelt, wo Sie sie für die Veröffentlichung im App Store Ihrer Organisation genehmigen können.

Weitere Informationen zur Verwendung der -API Graph zum Übermitteln von Apps finden Sie <a href="/graph/api/teamsapp-publish" target="_blank">hier.</a>

## <a name="validate"></a>Überprüfen

Auf der Seite <a href="/microsoftteams/manage-apps" target="_blank">Apps</a> verwalten im Microsoft Teams Admin Center (wechseln Sie in der linken Navigationsleiste zu **Teams** Apps verwalten), erhalten Sie einen Einblick in alle Teams-Apps für Ihre  >  Organisation. Mit **dem Widget Zur** Genehmigung ausstehend am oberen Rand der Seite können Sie sehen, wann eine benutzerdefinierte App zur Genehmigung eingereicht wird.

In der Tabelle zeigt eine neu übermittelte  App automatisch den **Veröffentlichungsstatus** Übermittelt und **den Status blockiert** **an.** Sie können die Spalte **Veröffentlichungsstatus** in absteigender Reihenfolge sortieren, um die App schnell zu finden.

![Veröffentlichungsstatus .](media/custom-app-lifecycle-validate-app.png)

Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln. Auf der **Registerkarte** "Informationen" können Sie Details zur App anzeigen, einschließlich Beschreibung, Status, Einreichungs- und App-ID.

![App-Detailseite für eine übermittelte App.](media/custom-app-lifecycle-app-details.png)

Weitere Informationen zur Verwendung der Graph-API zum Überprüfen des **Veröffentlichungsstatus finden** Sie <a href="/graph/api/appcatalogs-list-teamsapps" target="_blank">hier.</a>

## <a name="publish"></a>Veröffentlichen

Wenn Sie bereit sind, die App benutzern zur Verfügung zu stellen, veröffentlichen Sie die App.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken Sie auf den App-Namen, um zur  Seite mit den App-Details zu wechseln, und wählen Sie dann im Feld Veröffentlichungsstatus die Option Veröffentlichen **aus.**

    Nachdem Sie die App veröffentlicht haben, ändert sich der **Veröffentlichungsstatus** **in** Veröffentlicht, und **der Status** ändert sich automatisch in **Zulässig.**

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

![Seite "Apps" mit veröffentlichter App.](media/custom-app-lifecycle-discovery.png)

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um den Zugriff für die Benutzer zu ermöglichen, denen die Richtlinie zugewiesen wurde.

## <a name="update"></a>Aktualisieren

Zum Aktualisieren einer App sollten Entwickler weiterhin die Schritte im Abschnitt [Entwickeln](#develop) ausführen.

Wenn der Entwickler ein Update für eine veröffentlichte benutzerdefinierte App  übermittelt, werden Sie auf der Seite Apps verwalten im Widget Zur Genehmigung ausstehend <a href="/microsoftteams/manage-apps" target="_blank">benachrichtigt.</a> In der Tabelle wird der **Veröffentlichungsstatus** der App auf Übermittelt **aktualisieren festgelegt.**

![Seite "Apps verwalten" mit ausstehenden Anforderungen und dem App-Status .](media/custom-app-lifecycle-update-submitted.png)

So überprüfen und veröffentlichen Sie ein App-Update:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann **Update verfügbar** aus, um Die Details des Updates zu überprüfen.

    ![Seite "App-Details" aus.](media/custom-app-lifecycle-update-app.png)
3. Wenn Sie fertig sind, wählen Sie Veröffentlichen **aus,** um das Update zu veröffentlichen. Dadurch wird die vorhandene App ersetzt, die Versionsnummer aktualisiert und der **Veröffentlichungsstatus** in Veröffentlicht **geändert.** Alle App-Berechtigungs- und App-Setuprichtlinien bleiben für die aktualisierte App erhalten.

    Wenn Sie das Update ablehnen, bleibt die frühere Version der App veröffentlicht.

Beachten Sie Folgendes:

- Wenn eine App genehmigt wurde, kann jeder Benutzer ein Update für die App einreichen. Dies bedeutet, dass andere Entwickler , einschließlich des Entwicklers, der die App ursprünglich eingereicht hat, ein Update an die App übermitteln können.
- Wenn ein Entwickler eine App übermittelt und die Anforderung aussteht, kann nur dieser Entwickler ein Update an die App übermitteln. Andere Entwickler können ein Update erst dann übermitteln, wenn die App genehmigt wurde.

Weitere Informationen zur Verwendung der -API Graph zum Aktualisieren von Apps finden Sie <a href="/graph/api/teamsapp-update">hier.</a>

## <a name="related-topics"></a>Verwandte Themen

- [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](upload-custom-apps.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
- <a href="/graph/api/resources/teamsapp" target="_blank">Microsoft Graph-API für Teams-Apps</a>
